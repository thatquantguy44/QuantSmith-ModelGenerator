# SPEC — Asia–US Cross-Listed ADR Opening Auction Information Transfer
**ID:** QMG-20261120-20 · **Category:** DOMESTIC & GLOBAL MARKETS · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Local home-market closes and US ADR opening auctions occur asynchronously; simplistic close-to-open arbitrage ignores FX, share conversion and spreads. Decision: Choose hedge and execution timing for US ADR versus home-market overnight fair value.
- **H1:** An asynchronous local-information estimator reduces US ADR opening-price execution error beyond last local close plus FX conversion.
- **H0:** State-space asynchronous Kalman fair-value update using futures and related peer prices does not improve after-cost decision performance over Last home close × publicly known ADR conversion ratio × contemporaneous FX spot.
## Formulation and constraints
```text
FairADR_{i,t}=Ratio_i*LocalPrice_{i,homeclose}*FX_{i,t}+CrossMarketNews_{i,t}
```
Ratio_i is point-in-time ADR share ratio, FX has correct currency direction, CrossMarketNews is post-local close information known before US auction.
## Observation contract and time boundaries
**Grain:** ADR × home-market session × US opening-auction timestamp. **Fields:** Issuer depositary receipts ratios, local listings, public filings, FX quote timestamps, US ADR opening auctions, dividends and corporate action history.. **Availability:** Prevent local-price forward fill across sessions; ratio/corporate actions must be known at the US quote decision time..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible US ADRs and Korea/Japan/Taiwan/Hong Kong local shares decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Last home close × publicly known ADR conversion ratio × contemporaneous FX spot` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `State-space asynchronous Kalman fair-value update using futures and related peer prices` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `auction fair-value error, paired realized slippage, inventory risk, settlement/convertibility feasibility` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** ADR conversion fees, access restrictions, local holidays and stale home quotes create phantom arbitrage.
**Falsification:** No consistent opening execution improvement after financing, foreign exchange, depositary and auction spread costs.
**Production constraints:** ADR opening auction depth, ADR conversion channel capacity, local/US holiday and FX hedging constraints.
**Economic scenario (not a forecast):** $225k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $120k / $310k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -37.8% / 60.7%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
