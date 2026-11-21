# TOOLING — SFTR Reporting Regime Drift and Public-Private Divergence Detector
## Proposed Python stack — not installed or executed
`ruptures, statsmodels, pymc, polars`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/sftr_reporting_regime_drift/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Fixed ±3-sigma z-score alert on each series
- `candidate.py`: Robust multivariate Bayesian online change-point detection
- `constraints.py`: q is alarm threshold chosen before holdout; changes attributed to reporting are hypotheses until repository audit.
- `eval.py`: break detection delay, false alarms, post-correction economic interpretation stability
**Primary bottleneck:** Only public aggregate data may be available, making root-cause verification incomplete.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
