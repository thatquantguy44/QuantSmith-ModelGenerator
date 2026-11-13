# SPEC — Securities Lending Liquidity Provision Premium
**Status:** draft for approval · **ID:** QMG-20261112-11
## Problem and falsifiable hypothesis
Stable lenders may earn stress-sensitive compensation not captured by unconditional average fees.
- **Decision:** value dependable securities supply during high financing stress.
- **H1:** Stress supply resilience predicts financing yield beyond security composition and usage.
- **H0:** a feasible cost-inclusive implementation of `trailing revenue per lendable dollar` is not materially worse than the candidate.
## Mathematical formulation
```text
R_o,t=α_o+β_o×FinancingStress_t+ε_o,t
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Lender inventory changes, special fees, recalls, utilization, systemic stress factors. Grain: event time × instrument × counterparty/cohort, normalized for value dependable securities supply during high financing stress. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `value dependable securities supply during high financing stress` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `trailing revenue per lendable dollar`.
- **REQ-003:** define testable candidate `conditional financing factor decomposition` against the same opportunities.
- **REQ-004:** report `stress carry, stability, adjusted yield and mandate value` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** composition and survivorship bias can masquerade as a premium. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 1–3× is not verified.
