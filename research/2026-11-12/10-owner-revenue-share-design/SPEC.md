# SPEC — Beneficial-Owner Revenue-Sharing Mechanism
**Status:** draft for approval · **ID:** QMG-20261112-10
## Problem and falsifiable hypothesis
Fixed revenue share does not necessarily incentivize supply of scarce inventory.
- **Decision:** design fair participation-aware lending revenue splits.
- **H1:** Owner-segment elasticities enable arrangements increasing durable supply and both parties' net economics.
- **H0:** a feasible cost-inclusive implementation of `fixed schedule of revenue sharing` is not materially worse than the candidate.
## Mathematical formulation
```text
max_{α_o} Σ_o (1-α_o)Revenue_o[Inventory_o(α_o)] with owner participation
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** Owner fee splits, available holdings, program restrictions, lending volume and recalls. Grain: event time × instrument × counterparty/cohort, normalized for design fair participation-aware lending revenue splits. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `design fair participation-aware lending revenue splits` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `fixed schedule of revenue sharing`.
- **REQ-003:** define testable candidate `principal-agent participation and supply elasticity` against the same opportunities.
- **REQ-004:** report `new supply, agent revenue, owner revenue, program retention` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** unobservable selection and fairness/fiduciary restrictions. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 2–4× is not verified.
