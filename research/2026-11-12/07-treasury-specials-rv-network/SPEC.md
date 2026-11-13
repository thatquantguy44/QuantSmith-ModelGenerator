# SPEC — Treasury Specials Relative-Value Network
**Status:** draft for approval · **ID:** QMG-20261112-07
## Problem and falsifiable hypothesis
CUSIP-level specials reflect issuance, deliverability and hedging demand beyond generic collateral rates.
- **Decision:** identify executable repo RV across related Treasury CUSIPs.
- **H1:** A supply-aware graph explains and monetizes relative scarcity after full trading costs.
- **H0:** a feasible cost-inclusive implementation of `historical CUSIP z-score of specials` is not materially worse than the candidate.
## Mathematical formulation
```text
special_i=r_GC-r_repo_i; RV_ij=special_i-β_ij special_j
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** CUSIP-level repo and general-collateral rates, SOMA auctions, supply, futures basket, fails. Grain: event time × instrument × counterparty/cohort, normalized for identify executable repo RV across related Treasury CUSIPs. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `identify executable repo RV across related Treasury CUSIPs` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `historical CUSIP z-score of specials`.
- **REQ-003:** define testable candidate `CUSIP graph, cointegration and structural event controls` against the same opportunities.
- **REQ-004:** report `net spread convergence, realized returns, capital and fail risk` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** public SOMA cannot substitute for executable CUSIP quotes. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 2–4× is not verified.
