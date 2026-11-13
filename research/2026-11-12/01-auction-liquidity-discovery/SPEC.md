# SPEC — Auction-Based Securities Lending Liquidity Discovery
**Status:** draft for approval · **ID:** QMG-20261112-01
## Problem and falsifiable hypothesis
Only executed bilateral loan prices are observed; rejected locates censor willingness to pay.
- **Decision:** set fee and allocation for scarce lendable securities.
- **H1:** A structural auction policy improves net revenue over highest-fee-first after response and retention costs.
- **H0:** a feasible cost-inclusive implementation of `highest-fee-first feasible allocation` is not materially worse than the candidate.
## Mathematical formulation
```text
max Σ_c ∫(v_c(u)-k_c(u))du subject to Σ_c q_c≤I
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Timestamped locate quotes, revisions, rejects, fills, quantities and source-specific inventory. Grain: event time × instrument × counterparty/cohort, normalized for set fee and allocation for scarce lendable securities. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `set fee and allocation for scarce lendable securities` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `highest-fee-first feasible allocation`.
- **REQ-003:** define testable candidate `censored structural demand + constrained auction` against the same opportunities.
- **REQ-004:** report `net revenue, allocative efficiency, fill rate, churn and regret` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** censored demand, endogenous quote selection. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 3–6× is not verified.
