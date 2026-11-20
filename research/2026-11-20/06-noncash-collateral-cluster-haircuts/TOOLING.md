# TOOLING — Noncash Collateral Correlation-Cluster Haircut Controller
## Proposed Python stack — not installed or executed
`cvxpy, scipy, sklearn.covariance, polars`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/noncash_collateral_cluster_haircuts/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Uniform issuer/asset-class static haircut
- `candidate.py`: Scenario CVaR optimization with issuer cluster caps
- `constraints.py`: h is haircut vector, alpha tolerated tail probability and cap issuer concentration; credit/legal eligibility are hard constraints.
- `eval.py`: shortfall ES, collateral usage, haircut turnover, stress exceptions
**Primary bottleneck:** Asset covariance may break exactly when haircuts are needed and public free-float proxies omit liquidation controls.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
