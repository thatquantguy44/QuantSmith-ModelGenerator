# SPEC — Synthetic Borrow Supply via Options Parity
**Status:** draft for approval · **ID:** QMG-20261112-05
## Problem and falsifiable hypothesis
Physical borrow cost may diverge from implementable options/derivatives replication.
- **Decision:** choose physical versus synthetic financing exposure.
- **H1:** Parity-adjusted replication reduces funding cost for eligible positions after dividends and exercise risk.
- **H0:** a feasible cost-inclusive implementation of `physical borrow only` is not materially worse than the candidate.
## Mathematical formulation
```text
C-P≈S-PV(K)-PV(dividends)+borrow_adjustment; choose min total cost
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Options bid/ask, dividends, loan fees, stock price, funding, margin and assignment mechanics. Grain: event time × instrument × counterparty/cohort, normalized for choose physical versus synthetic financing exposure. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `choose physical versus synthetic financing exposure` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `physical borrow only`.
- **REQ-003:** define testable candidate `implied financing via corrected put-call parity` against the same opportunities.
- **REQ-004:** report `executable financing benefit, hedge error, margin and basis risk` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** American exercise and forecast-dividend mismatch. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 2–5× is not verified.
