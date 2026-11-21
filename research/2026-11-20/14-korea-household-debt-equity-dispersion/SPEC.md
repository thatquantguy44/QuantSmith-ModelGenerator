# SPEC — Korean Household Debt-Service Shock to Bank–Consumer Equity Spread
**ID:** QMG-20261120-14 · **Category:** DOMESTIC & GLOBAL MARKETS · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Aggregate debt service can change credit demand, asset quality and retail margins, but effects differ across lender and spending industries. Decision: Hedge relative exposure of Korean bank and consumer equities across household debt-service regime changes.
- **H1:** Lag-corrected Korean household DSR changes identify subsequent bank-versus-consumer earnings dispersion beyond policy rates/market beta.
- **H0:** Panel local projections with shrinkage and sector time fixed effects does not improve after-cost decision performance over Equal-beta long banks short consumer discretionary with lagged policy-rate signal.
## Formulation and constraints
```text
RelativeEPS_{b,c,t+h}=a+beta*DSRSurprise_t+gamma*PolicyRate_t+delta*FX_t+epsilon
```
b bank peer basket, c consumer peer basket, h disclosure-to-outcome window; DSRSurprise uses real-time expected vs published DSR, not revised future panels.
## Observation contract and time boundaries
**Grain:** quarterly DSR release × issuer × accounting period × price timestamp. **Fields:** BIS Korea household DSR, BOK/Statistics Korea public lending/rates, issuer earnings and local equity returns, reporting vintage.. **Availability:** BIS Korean DSR published with quarterly lag (available through 2026-Q1 on checked dataset page); do not trade on 2026-Q2 unless publicly released..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible South Korea household credit, KOSPI/KOSDAQ banks and consumer discretionary decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Equal-beta long banks short consumer discretionary with lagged policy-rate signal` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Panel local projections with shrinkage and sector time fixed effects` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `cross-sector earnings forecast delta, beta-neutral IR, worst-regime drawdown, capacity after local spreads` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Endogenous rate policy and sector composition cause confounding; public issuer histories need delisting continuity.
**Falsification:** No stable expected-earnings or beta-neutral sector difference once rates and economy factors are controlled.
**Production constraints:** Local borrow, FX hedge, Korean market access, corporate action history, sector liquidity and taxes.
**Economic scenario (not a forecast):** $170k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $105k / $260k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -22.8% / 91.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
