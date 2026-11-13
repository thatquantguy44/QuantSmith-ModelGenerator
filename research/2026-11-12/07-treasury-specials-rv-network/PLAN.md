# PLAN — Treasury Specials Relative-Value Network
**Status:** architecture proposed, not implemented.
## Components
`approved source adapter → time/entitlement gate → normalized treasury-specials-rv-network panel → costed baseline → CUSIP graph, cointegration and structural event controls → matched policy replay → risk and source ledger → reviewer`.
## Data contracts and integrity
Require CUSIP-level repo and general-collateral rates, SOMA auctions, supply, futures basket, fails. Each record must have an immutable identity and time available to the desk before the action. Explicitly test false legal eligibility and missing prices. Use synthetic fixture inputs until valid data rights are confirmed.
## Modeling choices
- Baseline: **historical CUSIP z-score of specials**.
- Initial candidate: **CUSIP graph, cointegration and structural event controls**.
- Research-only advanced alternative: **dynamic security-specific financing equilibrium**.
- Economics: compare same feasible inventory/funding and transaction-cost universe. Do not assume prices/executions or financing capacity that was never available.
## Interfaces
`load(as_of, source_ids)`, `normalize(events, clock)`, `baseline(state)`, `candidate(state)`, `evaluate(holdout)`, `render_evidence()` are **proposed** interfaces only.
## Verification and traceability
REQ-001→T-001,T-002; REQ-002→T-003; REQ-003→T-004,T-005; REQ-004→T-006,T-007; NFR-001/002→T-002,T-008. Evaluate net spread convergence, realized returns, capital and fail risk on pre-registered temporal holdout. Stress **public SOMA cannot substitute for executable CUSIP quotes**.
## Operational envelope
Start with offline replay and shadow mode. Use kill switch to fall back to baseline. No code or deployment changes are included in this PR.
