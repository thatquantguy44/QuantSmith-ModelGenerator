# SPEC — Repo Term Structure Dislocation Engine
**Status:** draft for approval · **ID:** QMG-20261112-02
## Problem and falsifiable hypothesis
Observed term repo spreads incorporate collateral scarcity and balance-sheet constraints besides expected overnight rates.
- **Decision:** choose term financing maturity and collateral route.
- **H1:** A collateral-aware funding curve beats overnight rolling after executable financing costs.
- **H0:** a feasible cost-inclusive implementation of `overnight funding rollover` is not materially worse than the candidate.
## Mathematical formulation
```text
Basis(T)=r_repo(T)-T^-1∫E_t[r_ON(u)]du-collateral_carry(T)
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Repo rate/tenor quotes, SOFR, collateral CUSIP, haircut, balance-sheet dates. Grain: event time × instrument × counterparty/cohort, normalized for choose term financing maturity and collateral route. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `choose term financing maturity and collateral route` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `overnight funding rollover`.
- **REQ-003:** define testable candidate `security-aware no-arbitrage term curve` against the same opportunities.
- **REQ-004:** report `after-cost funding savings, basis convergence, risk and drawdown` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** indicative prices and bid/ask execution mismatch. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 2–5× is not verified.
