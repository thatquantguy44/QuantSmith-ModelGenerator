# TOOLING — US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface
## Proposed Python stack — not installed or executed
`numpy, scipy, pandas, quantlib-python`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/us_tips_indexation_lag_carry/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Duration-matched TIPS-minus-nominal bond without CPI-calendar signal
- `candidate.py`: Deterministic index-ratio accrual and liquidity-factor attribution
- `constraints.py`: KnownIndexAccrual_t is observable at decision time; carry, breakeven and real-yield exposures require duration scaling and deflation floors.
- `eval.py`: hedge tracking error, information ratio net of costs, index replication error, carry decomposition residual
**Primary bottleneck:** Illiquid issue quotations, inflation floor optionality, unrevised CPI data and seasonality overfit.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
