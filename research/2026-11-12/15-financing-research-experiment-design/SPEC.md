# SPEC — Optimal Financing Research Experiment Design
**Status:** draft for approval · **ID:** QMG-20261112-15
## Problem and falsifiable hypothesis
Quant teams spend constrained time on uncertain ideas without common decision-value criteria.
- **Decision:** allocate scarce research effort to high information-value experiments.
- **H1:** Expected value of sample information improves go/no-go efficiency over equal research budgets.
- **H0:** a feasible cost-inclusive implementation of `equal effort per idea` is not materially worse than the candidate.
## Mathematical formulation
```text
experiment*=argmax_e{E[max_a Value(a)|new information_e]-max_a E[Value(a)]-Cost(e)}
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Experiment budgets, model alternatives, synthetic case studies, past evidence quality and reproducibility logs. Grain: event time × instrument × counterparty/cohort, normalized for allocate scarce research effort to high information-value experiments. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `allocate scarce research effort to high information-value experiments` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `equal effort per idea`.
- **REQ-003:** define testable candidate `Bayesian value-of-information and sequential experiment selection` against the same opportunities.
- **REQ-004:** report `decision value per research hour, false discovery, stopping time and deployed value` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** retrospective outcomes are selectively recorded and success probabilities subjective. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 2–5× is not verified.
