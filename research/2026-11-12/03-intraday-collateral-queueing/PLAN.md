# PLAN — Intraday Collateral Liquidity Forecasting via Queueing Theory
**Status:** architecture proposed, not implemented.
## Components
`approved source adapter → time/entitlement gate → normalized intraday-collateral-queueing panel → costed baseline → stochastic queueing and priority model → matched policy replay → risk and source ledger → reviewer`.
## Data contracts and integrity
Require Intraday margin calls, settlement timestamps, queue lengths, cash/collateral buffers, fails. Each record must have an immutable identity and time available to the desk before the action. Explicitly test false legal eligibility and missing prices. Use synthetic fixture inputs until valid data rights are confirmed.
## Modeling choices
- Baseline: **fixed intraday liquidity reserve**.
- Initial candidate: **stochastic queueing and priority model**.
- Research-only advanced alternative: **model predictive control with chance-constrained service levels**.
- Economics: compare same feasible inventory/funding and transaction-cost universe. Do not assume prices/executions or financing capacity that was never available.
## Interfaces
`load(as_of, source_ids)`, `normalize(events, clock)`, `baseline(state)`, `candidate(state)`, `evaluate(holdout)`, `render_evidence()` are **proposed** interfaces only.
## Verification and traceability
REQ-001→T-001,T-002; REQ-002→T-003; REQ-003→T-004,T-005; REQ-004→T-006,T-007; NFR-001/002→T-002,T-008. Evaluate liquidity buffer cost, p99 delay, shortfalls and failures on pre-registered temporal holdout. Stress **timestamp quality and hidden queue-priority rules**.
## Operational envelope
Start with offline replay and shadow mode. Use kill switch to fall back to baseline. No code or deployment changes are included in this PR.
