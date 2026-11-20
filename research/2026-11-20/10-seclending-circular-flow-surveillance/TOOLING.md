# TOOLING — Securities-Lending Circular Flow Surveillance via Temporal Graphs
## Proposed Python stack — not installed or executed
`networkx, polars, pydantic, pytest`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/seclending_circular_flow_surveillance/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Two-party net-quantity turnaround rules
- `candidate.py`: Temporal graph motif detection with exact deterministic event identity
- `constraints.py`: K is review budget; temporal motif score must be conditioned on legitimate inventory transfers and settlement cycles.
- `eval.py`: precision at K, seeded motif recall, legitimate-flow false-alerts, explanation fidelity
**Primary bottleneck:** False accusations, privileged customer data, and severe sample-selection bias in investigated cases.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
