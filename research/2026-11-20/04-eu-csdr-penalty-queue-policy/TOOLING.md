# TOOLING — European CSDR Penalty-Aware Settlement Queue Prioritization
## Proposed Python stack — not installed or executed
`ortools, simpy, pydantic, pytest`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/eu_csdr_penalty_queue_policy/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: FIFO or largest-notional-first allowed settlement priority
- `candidate.py`: Constrained weighted-shortest-processing-time queue policy with eligibility rules
- `constraints.py`: pi is processing sequence, i instruction, penalty_i applies only under effective CSDR exclusions and jurisdictional rules; capacity_t is eligible CSD processing capacity.
- `eval.py`: penalty liability, fail-days, priority-rule violations, operational throughput
**Primary bottleneck:** Misclassification of non-attributable fail causes or legal exclusion yields incorrect optimized queues.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
