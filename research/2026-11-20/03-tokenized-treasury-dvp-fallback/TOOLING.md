# TOOLING — Tokenized Treasury Collateral DvP Finality and Fallback Stress
## Proposed Python stack — not installed or executed
`python-statemachine, networkx, hypothesis, pytest`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/tokenized_treasury_dvp_fallback/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Conventional permitted book-entry DvP with settlement cutoff
- `candidate.py`: Timed Petri net state-machine model of mint/transfer/burn and escrow/finality rules
- `constraints.py`: r is a legally eligible path; require validated ownership, wallet permission, finality evidence, and a deterministic fallback if one leg fails.
- `eval.py`: liquidity-hours locked, failed atomicity scenarios, rollback time, eligible-settlement capacity
**Primary bottleneck:** Token entitlements must not be treated as interchangeable with every conventional collateral/clearing agreement.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
