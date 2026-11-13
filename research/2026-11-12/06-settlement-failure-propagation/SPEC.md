# SPEC — Collateral Settlement Failure Propagation
**Status:** draft for approval · **ID:** QMG-20261112-06
## Problem and falsifiable hypothesis
A failed transfer can block related collateral deliveries and financing obligations.
- **Decision:** target the settlement legs whose failure causes the most downstream loss.
- **H1:** Network preventive routing reduces aggregate failed obligations relative to isolated fail scoring.
- **H0:** a feasible cost-inclusive implementation of `FIFO escalation by individual settlement` is not materially worse than the candidate.
## Mathematical formulation
```text
ExpectedLoss(G,action) versus ExpectedLoss(G minus failed edges,action)
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Dependency-linked settlement legs, legal routes, timestamps, collateral and failed instructions. Grain: event time × instrument × counterparty/cohort, normalized for target the settlement legs whose failure causes the most downstream loss. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `target the settlement legs whose failure causes the most downstream loss` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `FIFO escalation by individual settlement`.
- **REQ-003:** define testable candidate `directed graph contagion replay` against the same opportunities.
- **REQ-004:** report `cascade size, failed notional, recovery time and funding cost` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** incomplete external dependencies and cross-entity visibility. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 2–4× is not verified.
