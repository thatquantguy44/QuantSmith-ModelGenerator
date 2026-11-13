# SPEC — Borrower Default Wrong-Way Risk Optimization
**Status:** draft for approval · **ID:** QMG-20261112-04
## Problem and falsifiable hypothesis
Borrower default can coincide with loaned-security appreciation and collateral liquidation stress.
- **Decision:** price borrower limits, haircut and contingent indemnification.
- **H1:** Joint default-exposure modeling finds stressed loss missed by independent PD/haircut rules.
- **H0:** a feasible cost-inclusive implementation of `independent PD times static haircut` is not materially worse than the candidate.
## Mathematical formulation
```text
Loss=1{default≤T}×max(ReplacementValue-CollateralProceeds,0)
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Counterparty credit, collateral, contract closeout provisions, stress price and liquidity history. Grain: event time × instrument × counterparty/cohort, normalized for price borrower limits, haircut and contingent indemnification. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `price borrower limits, haircut and contingent indemnification` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `independent PD times static haircut`.
- **REQ-003:** define testable candidate `correlated default/exposure Monte Carlo` against the same opportunities.
- **REQ-004:** report `stress ES, loss calibration, limits used and risk-adjusted P&L` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** sparse default observations and unidentifiable tail parameters. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 2–4× is not verified.
