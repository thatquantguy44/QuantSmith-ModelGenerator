# TOOLING — Cyber-Outage Contingent Repo Funding Recovery Routes
## Proposed Python stack — not installed or executed
`networkx, scipy, cvxpy, simpy`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/repo_cyber_funding_recovery/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Fixed 10% contingency funding buffer with one permitted fallback
- `candidate.py`: Two-stage robust multi-commodity flow with cyber failure scenarios
- `constraints.py`: x are route and lender allocation decisions, b is reserved liquidity, p_s is the unit shortfall penalty in outage scenario s; legal availability, committed limits and collateral eligibility bound x.
- `eval.py`: shortfall dollars, p95 duration, liquidity carry, fail probability, recovery cost
**Primary bottleneck:** Public aggregates cannot recover the bank-level cash-lender network or prove an actual route is legally available.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
