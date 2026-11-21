# SPEC — EU ETS Auction Supply Revision and Carbon Futures Carry
**ID:** QMG-20261120-13 · **Category:** DOMESTIC & GLOBAL MARKETS · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Auction calendar revisions and annual compliance data affect expected allowance net supply but are released on distinct clocks. Decision: Hedge EUA futures calendar spreads against only announced changes in auction volume and verified-emissions obligations.
- **H1:** Public-vintage auction-volume shocks improve calendar-spread/hedge-risk forecasts beyond front-month momentum and seasonal dummies.
- **H0:** Event study of auction schedule revisions and futures risk factors does not improve after-cost decision performance over Calendar-month fixed seasonal allowance spread.
## Formulation and constraints
```text
Spread_{m,n,t}=theta*(ExpectedAuctionSupply_t - ExpectedComplianceDemand_t)+beta*EnergyControls_t+epsilon_t
```
m,n are contract maturities; expectations only use public revisions available before trade, not full-year realized auction volumes.
## Observation contract and time boundaries
**Grain:** EU ETS auction calendar publication × allowance futures tenor × exchange quote timestamp. **Fields:** European Commission vintage auction calendars, Union Registry verified emissions/compliance, dated policy changes, EUA/power/gas contract prices.. **Availability:** 2027 auction schedule announced Jul 30 2026; 2025 compliance data public Oct 5 2026; only released data at as-of permitted..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible EU carbon allowances (EUA), European power utilities decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Calendar-month fixed seasonal allowance spread` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Event study of auction schedule revisions and futures risk factors` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `EUA spread basis MAE, hedged risk reduction, net carry after fees, low-liquidity scenario loss` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Policy revision expectations may be priced before official publication; futures/Registry coverage not contemporaneous.
**Falsification:** No out-of-sample spread forecast or hedge benefit net of spreads after matched energy factors.
**Production constraints:** EUA contract liquidity, expiry rolling, carbon compliance mandates and margin/collateral limits.
**Economic scenario (not a forecast):** $210k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $125k / $310k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -25.6% / 84.5%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
