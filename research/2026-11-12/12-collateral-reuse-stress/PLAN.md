# PLAN — Collateral Reuse Chain Stress Testing
**Status:** architecture proposed, not implemented.
## Components
`approved source adapter → time/entitlement gate → normalized collateral-reuse-stress panel → costed baseline → legal reuse network input-output simulation → matched policy replay → risk and source ledger → reviewer`.
## Data contracts and integrity
Require Source provenance, permissioned reuse contracts, collateral movements, haircut and margin events. Each record must have an immutable identity and time available to the desk before the action. Explicitly test false legal eligibility and missing prices. Use synthetic fixture inputs until valid data rights are confirmed.
## Modeling choices
- Baseline: **gross collateral stock and static stress**.
- Initial candidate: **legal reuse network input-output simulation**.
- Research-only advanced alternative: **dynamic network cascades with haircuts and intraday liquidity**.
- Economics: compare same feasible inventory/funding and transaction-cost universe. Do not assume prices/executions or financing capacity that was never available.
## Interfaces
`load(as_of, source_ids)`, `normalize(events, clock)`, `baseline(state)`, `candidate(state)`, `evaluate(holdout)`, `render_evidence()` are **proposed** interfaces only.
## Verification and traceability
REQ-001→T-001,T-002; REQ-002→T-003; REQ-003→T-004,T-005; REQ-004→T-006,T-007; NFR-001/002→T-002,T-008. Evaluate capacity contraction, margin calls, recovery time and chain failure on pre-registered temporal holdout. Stress **double counting and unsupported rehypothecation rights**.
## Operational envelope
Start with offline replay and shadow mode. Use kill switch to fall back to baseline. No code or deployment changes are included in this PR.
