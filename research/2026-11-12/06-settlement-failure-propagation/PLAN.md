# PLAN — Collateral Settlement Failure Propagation
**Status:** architecture proposed, not implemented.
## Components
`approved source adapter → time/entitlement gate → normalized settlement-failure-propagation panel → costed baseline → directed graph contagion replay → matched policy replay → risk and source ledger → reviewer`.
## Data contracts and integrity
Require Dependency-linked settlement legs, legal routes, timestamps, collateral and failed instructions. Each record must have an immutable identity and time available to the desk before the action. Explicitly test false legal eligibility and missing prices. Use synthetic fixture inputs until valid data rights are confirmed.
## Modeling choices
- Baseline: **FIFO escalation by individual settlement**.
- Initial candidate: **directed graph contagion replay**.
- Research-only advanced alternative: **stochastic hypergraph scheduling and recovery routing**.
- Economics: compare same feasible inventory/funding and transaction-cost universe. Do not assume prices/executions or financing capacity that was never available.
## Interfaces
`load(as_of, source_ids)`, `normalize(events, clock)`, `baseline(state)`, `candidate(state)`, `evaluate(holdout)`, `render_evidence()` are **proposed** interfaces only.
## Verification and traceability
REQ-001→T-001,T-002; REQ-002→T-003; REQ-003→T-004,T-005; REQ-004→T-006,T-007; NFR-001/002→T-002,T-008. Evaluate cascade size, failed notional, recovery time and funding cost on pre-registered temporal holdout. Stress **incomplete external dependencies and cross-entity visibility**.
## Operational envelope
Start with offline replay and shadow mode. Use kill switch to fall back to baseline. No code or deployment changes are included in this PR.
