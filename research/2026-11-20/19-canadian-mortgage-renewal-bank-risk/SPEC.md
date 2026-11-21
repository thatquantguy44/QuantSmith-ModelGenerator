# SPEC — Canadian Mortgage Renewal Cohorts to Bank Credit-Risk Dispersion
**ID:** QMG-20261120-19 · **Category:** DOMESTIC & GLOBAL MARKETS · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Fixed-mortgage renewal resets vary across vintage cohorts, producing delayed stress without an immediate change in aggregate debt stock. Decision: Hedge Canadian bank credit/equity risk using public maturity-cohort mortgage renewal exposure rather than broad unemployment alone.
- **H1:** Estimated vintage-conditioned payment shock predicts cross-bank loan loss and valuation dispersion beyond level rates and employment controls.
- **H0:** Vintage-cohort mortgage reset microsimulation from public aggregates does not improve after-cost decision performance over Bank loss sensitivity to national unemployment and policy rate alone.
## Formulation and constraints
```text
Shock_{cohort,t}=Balance_{cohort}*max(RenewalPayment_t-OldPayment,0); ECL_{bank,t+h}=beta*Shock+controls
```
Balance is refinanceable exposure (public aggregate proxy initially), ECL expected credit loss; individual bank vintage mapping may be incomplete.
## Observation contract and time boundaries
**Grain:** Canadian mortgage cohort × monthly public release × bank quarterly filing. **Fields:** Bank of Canada public mortgage balances/rates, staff renewal methodology, bank annual/quarterly mortgage disclosures, CAD rate and housing data.. **Availability:** Use released monthly tables and historical market expectations before renewal; a 2025 note's projected 2026 payments are scenario assumptions, not observed outcomes..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible Canadian banks, mortgage credit and bank equity/CDS decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Bank loss sensitivity to national unemployment and policy rate alone` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Vintage-cohort mortgage reset microsimulation from public aggregates` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `future loss forecast gain, bank-spread risk hedging, sensitivity to vintage assumptions, net hedging cost` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Public aggregate cohorts do not identify each bank's borrower vintage distribution or underwriting quality.
**Falsification:** No cross-bank predictive signal after public loan books and unemployment/rate controls, or estimates too wide to act on.
**Production constraints:** TSX bank/equity/CDS liquidity, CAD FX basis, sector beta hedges and credit market impact.
**Economic scenario (not a forecast):** $160k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 8 months; annual gross benefit scenarios $0k / $105k / $240k (downside/base/upside) for the remaining 1.3333333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -12.5% / 100.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
