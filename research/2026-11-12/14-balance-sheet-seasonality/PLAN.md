# PLAN — Balance-Sheet Seasonality Arbitrage
**Status:** architecture proposed, not implemented.
## Components
`approved source adapter → time/entitlement gate → normalized balance-sheet-seasonality panel → costed baseline → calendar event study with capacity-aware optimization → matched policy replay → risk and source ledger → reviewer`.
## Data contracts and integrity
Require Repo spread term structure, settlement calendar, quarter-end dates, financing usage. Each record must have an immutable identity and time available to the desk before the action. Explicitly test false legal eligibility and missing prices. Use synthetic fixture inputs until valid data rights are confirmed.
## Modeling choices
- Baseline: **constant overnight-roll financing**.
- Initial candidate: **calendar event study with capacity-aware optimization**.
- Research-only advanced alternative: **stochastic dynamic capacity control under regime variation**.
- Economics: compare same feasible inventory/funding and transaction-cost universe. Do not assume prices/executions or financing capacity that was never available.
## Interfaces
`load(as_of, source_ids)`, `normalize(events, clock)`, `baseline(state)`, `candidate(state)`, `evaluate(holdout)`, `render_evidence()` are **proposed** interfaces only.
## Verification and traceability
REQ-001→T-001,T-002; REQ-002→T-003; REQ-003→T-004,T-005; REQ-004→T-006,T-007; NFR-001/002→T-002,T-008. Evaluate holdout funding cost, stress liquidity, rollover risk and drawdown on pre-registered temporal holdout. Stress **well-known quarter-end effects may already be fully priced**.
## Operational envelope
Start with offline replay and shadow mode. Use kill switch to fall back to baseline. No code or deployment changes are included in this PR.
