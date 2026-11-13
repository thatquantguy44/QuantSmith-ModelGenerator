# SPEC — Balance-Sheet Seasonality Arbitrage
**Status:** draft for approval · **ID:** QMG-20261112-14
## Problem and falsifiable hypothesis
Calendar events create predictable seasonal changes in constrained funding supply.
- **Decision:** choose funding tenor and capacity reserves around reporting dates.
- **H1:** Calendar-aware funding reduces ex-ante cost on unseen quarter-ends after realistic balance-sheet charges.
- **H0:** a feasible cost-inclusive implementation of `constant overnight-roll financing` is not materially worse than the candidate.
## Mathematical formulation
```text
max Σ_t [financing revenue_t-funding_t-λ_t×capacity_t] under capacity limits
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Repo spread term structure, settlement calendar, quarter-end dates, financing usage. Grain: event time × instrument × counterparty/cohort, normalized for choose funding tenor and capacity reserves around reporting dates. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `choose funding tenor and capacity reserves around reporting dates` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `constant overnight-roll financing`.
- **REQ-003:** define testable candidate `calendar event study with capacity-aware optimization` against the same opportunities.
- **REQ-004:** report `holdout funding cost, stress liquidity, rollover risk and drawdown` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** well-known quarter-end effects may already be fully priced. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 2–4× is not verified.
