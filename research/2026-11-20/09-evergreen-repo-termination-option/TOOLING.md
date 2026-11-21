# TOOLING — Evergreen Repo Early-Termination Optionality Risk Budget
## Proposed Python stack — not installed or executed
`numpy, scipy, statsmodels, numba`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/evergreen_repo_termination_option/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Static repo spread plus deterministic notice-day funding reserve
- `candidate.py`: Least-squares Monte Carlo for bilateral asymmetric stop decisions
- `constraints.py`: exercise and continuation are contract-party-specific; funder and borrower exercise incentives must be separately simulated.
- `eval.py`: replacement funding loss, option premium calibration, cash-flow stress, tail liquidity gap
**Primary bottleneck:** Non-observed counterparty exercise behavior; public term repo alone does not identify proprietary notice clauses.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
