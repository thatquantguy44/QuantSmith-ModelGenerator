# SPEC — US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface
**ID:** QMG-20261120-12 · **Category:** DOMESTIC & GLOBAL MARKETS · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
TIPS index ratio uses reference CPI with publication lag; naïve inflation beta ignores fixed-known indexation accrual and deflation mechanics. Decision: Select TIPS versus nominal duration-hedged exposure around CPI index-ratio carry windows.
- **H1:** A vintage-consistent carry decomposition improves matched-duration real-vs-nominal excess-return hedging net of liquidity/rollover costs.
- **H0:** Deterministic index-ratio accrual and liquidity-factor attribution does not improve after-cost decision performance over Duration-matched TIPS-minus-nominal bond without CPI-calendar signal.
## Formulation and constraints
```text
TIPSReturn_t=RealYieldReturn_t+KnownIndexAccrual_t+InflationNews_t+LiquidityResidual_t
```
KnownIndexAccrual_t is observable at decision time; carry, breakeven and real-yield exposures require duration scaling and deflation floors.
## Observation contract and time boundaries
**Grain:** TIPS CUSIP × CPI/index-ratio effective date × decision timestamp. **Fields:** Treasury official daily TIPS index ratios/CPI, vintage BLS CPI, nominal/TIPS quotes, issue terms, accrued interest.. **Availability:** Daily index ratios can be forecast only from already published reference CPI; preserve first release and later corrections..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible US TIPS, nominal Treasuries, inflation swaps decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Duration-matched TIPS-minus-nominal bond without CPI-calendar signal` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Deterministic index-ratio accrual and liquidity-factor attribution` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `hedge tracking error, information ratio net of costs, index replication error, carry decomposition residual` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Illiquid issue quotations, inflation floor optionality, unrevised CPI data and seasonality overfit.
**Falsification:** Improvement vanishes versus a carry-only and time-matched duration hedge after execution spread costs.
**Production constraints:** Issue-level depth, coupon accrued interest, repo funding, bid-ask, tax and duration hedging constraints.
**Economic scenario (not a forecast):** $135k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $105k / $200k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 16.7% / 122.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
