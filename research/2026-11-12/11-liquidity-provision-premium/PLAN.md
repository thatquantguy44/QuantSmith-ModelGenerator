# PLAN — Securities Lending Liquidity Provision Premium
**Status:** architecture proposed, not implemented.
## Components
`approved source adapter → time/entitlement gate → normalized liquidity-provision-premium panel → costed baseline → conditional financing factor decomposition → matched policy replay → risk and source ledger → reviewer`.
## Data contracts and integrity
Require Lender inventory changes, special fees, recalls, utilization, systemic stress factors. Each record must have an immutable identity and time available to the desk before the action. Explicitly test false legal eligibility and missing prices. Use synthetic fixture inputs until valid data rights are confirmed.
## Modeling choices
- Baseline: **trailing revenue per lendable dollar**.
- Initial candidate: **conditional financing factor decomposition**.
- Research-only advanced alternative: **endogenous supply/fee equilibrium with nonlinear downside beta**.
- Economics: compare same feasible inventory/funding and transaction-cost universe. Do not assume prices/executions or financing capacity that was never available.
## Interfaces
`load(as_of, source_ids)`, `normalize(events, clock)`, `baseline(state)`, `candidate(state)`, `evaluate(holdout)`, `render_evidence()` are **proposed** interfaces only.
## Verification and traceability
REQ-001→T-001,T-002; REQ-002→T-003; REQ-003→T-004,T-005; REQ-004→T-006,T-007; NFR-001/002→T-002,T-008. Evaluate stress carry, stability, adjusted yield and mandate value on pre-registered temporal holdout. Stress **composition and survivorship bias can masquerade as a premium**.
## Operational envelope
Start with offline replay and shadow mode. Use kill switch to fall back to baseline. No code or deployment changes are included in this PR.
