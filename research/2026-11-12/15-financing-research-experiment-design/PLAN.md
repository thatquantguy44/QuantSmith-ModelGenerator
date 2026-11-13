# PLAN — Optimal Financing Research Experiment Design
**Status:** architecture proposed, not implemented.
## Components
`approved source adapter → time/entitlement gate → normalized financing-research-experiment-design panel → costed baseline → Bayesian value-of-information and sequential experiment selection → matched policy replay → risk and source ledger → reviewer`.
## Data contracts and integrity
Require Experiment budgets, model alternatives, synthetic case studies, past evidence quality and reproducibility logs. Each record must have an immutable identity and time available to the desk before the action. Explicitly test false legal eligibility and missing prices. Use synthetic fixture inputs until valid data rights are confirmed.
## Modeling choices
- Baseline: **equal effort per idea**.
- Initial candidate: **Bayesian value-of-information and sequential experiment selection**.
- Research-only advanced alternative: **knowledge-gradient portfolio policy with correlated research tasks**.
- Economics: compare same feasible inventory/funding and transaction-cost universe. Do not assume prices/executions or financing capacity that was never available.
## Interfaces
`load(as_of, source_ids)`, `normalize(events, clock)`, `baseline(state)`, `candidate(state)`, `evaluate(holdout)`, `render_evidence()` are **proposed** interfaces only.
## Verification and traceability
REQ-001→T-001,T-002; REQ-002→T-003; REQ-003→T-004,T-005; REQ-004→T-006,T-007; NFR-001/002→T-002,T-008. Evaluate decision value per research hour, false discovery, stopping time and deployed value on pre-registered temporal holdout. Stress **retrospective outcomes are selectively recorded and success probabilities subjective**.
## Operational envelope
Start with offline replay and shadow mode. Use kill switch to fall back to baseline. No code or deployment changes are included in this PR.
