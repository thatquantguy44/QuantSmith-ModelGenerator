# SPEC — Collateral Reuse Chain Stress Testing
**Status:** draft for approval · **ID:** QMG-20261112-12
## Problem and falsifiable hypothesis
Legal reuse increases effective capacity but creates hidden dependence on settlement and margin links.
- **Decision:** set buffers and resilience policies for eligible collateral transformation chains.
- **H1:** Provenance-aware reuse graph explains stress contractions beyond gross reused collateral.
- **H0:** a feasible cost-inclusive implementation of `gross collateral stock and static stress` is not materially worse than the candidate.
## Mathematical formulation
```text
I_effective=(Identity-A)^-1 I_base when spectral_radius(A)<1
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Source provenance, permissioned reuse contracts, collateral movements, haircut and margin events. Grain: event time × instrument × counterparty/cohort, normalized for set buffers and resilience policies for eligible collateral transformation chains. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `set buffers and resilience policies for eligible collateral transformation chains` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `gross collateral stock and static stress`.
- **REQ-003:** define testable candidate `legal reuse network input-output simulation` against the same opportunities.
- **REQ-004:** report `capacity contraction, margin calls, recovery time and chain failure` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** double counting and unsupported rehypothecation rights. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 1–4× is not verified.
