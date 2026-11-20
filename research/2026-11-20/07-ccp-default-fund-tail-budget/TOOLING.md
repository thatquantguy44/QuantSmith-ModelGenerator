# TOOLING — CCP Default-Fund Mutualization Marginal Risk Budget
## Proposed Python stack — not installed or executed
`numpy, scipy, cvxpy, numba`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/ccp_default_fund_tail_budget/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Exposure limit proportional to initial margin only
- `candidate.py`: Transparent worst-two-member default waterfall simulator
- `constraints.py`: j clearing membership or CCP, s default scenario, alpha stress-tail quantile; actual waterfall order and limits are CCP specific.
- `eval.py`: tail capital charge, stress shortfall, liquidity buffer usage, net clearing benefit
**Primary bottleneck:** Actual default fund contributions and replenishment terms may differ from public examples and vary by venue.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
