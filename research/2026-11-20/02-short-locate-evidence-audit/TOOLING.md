# TOOLING — Reg SHO Locate Evidence and Borrow-Capacity Audit Engine
## Proposed Python stack — not installed or executed
`pydantic, polars, duckdb, pytest`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/short_locate_evidence_audit/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: End-of-day deterministic locate exception SQL rules
- `candidate.py`: Typed event-sourcing finite-state verification with causal explainability
- `constraints.py`: FN is an incorrectly accepted exception, FP an incorrectly blocked valid locate, and Delay is processing latency; all compliance rules require human-verified effective policy and exemptions.
- `eval.py`: prevented invalid requests, false blocks, recall error, audit completion time, p99 latency
**Primary bottleneck:** Reg SHO exemptions, broker responsibilities and settlement rules require qualified legal interpretation.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
