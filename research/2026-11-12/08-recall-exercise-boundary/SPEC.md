# SPEC — Loan Recall Early-Exercise Boundary
**Status:** draft for approval · **ID:** QMG-20261112-08
## Problem and falsifiable hypothesis
Loans can end early due to governance, sale or liquidity rights that constrain inventory.
- **Decision:** forecast compliant beneficial-owner recall exercise and source replacement.
- **H1:** Owner-specific early-exercise states predict recall timing and lower replacement exposure.
- **H0:** a feasible cost-inclusive implementation of `constant owner-specific recall probability` is not materially worse than the candidate.
## Mathematical formulation
```text
V_t=max(V_recall,t, E_t[carry_t+discount×V_t+1])
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Loan age, fee, recalls, corporate action calendar, owner restrictions, replacement cost. Grain: event time × instrument × counterparty/cohort, normalized for forecast compliant beneficial-owner recall exercise and source replacement. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `forecast compliant beneficial-owner recall exercise and source replacement` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `constant owner-specific recall probability`.
- **REQ-003:** define testable candidate `constrained survival and stopping model` against the same opportunities.
- **REQ-004:** report `recall warning, replacement cost, calibration and fail prevention` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** governance and fiduciary rights cannot be traded away. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 2–4× is not verified.
