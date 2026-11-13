# SPEC — Cross-Currency Repo Basis Optimization
**Status:** draft for approval · **ID:** QMG-20261112-09
## Problem and falsifiable hypothesis
Different currency repo and FX swap combinations can create cost differences after all frictions.
- **Decision:** choose FX-hedged financing currency and legal collateral path.
- **H1:** CIP-adjusted multi-currency routing beats domestic-only financing where transferable collateral exists.
- **H0:** a feasible cost-inclusive implementation of `domestic collateral and repo only` is not materially worse than the candidate.
## Mathematical formulation
```text
USD-equivalent rate=foreign repo rate+FX hedge+basis+collateral/capital costs
```
Units, exposure direction and feasibility constraints must be signed off before numerical implementation.
## Data contract
**Required fields:** FX swaps, currencies, tenor rates, haircuts, FX settlements, taxes, legal eligibility. Grain: event time × instrument × counterparty/cohort, normalized for choose FX-hedged financing currency and legal collateral path. Preserve event timestamp, information-available timestamp, source/vintage, legal permissions, missingness and revision history.
## Requirements
- **REQ-001:** represent the decision `choose FX-hedged financing currency and legal collateral path` and legal/operational feasibility.
- **REQ-002:** implement deterministic cost-inclusive baseline `domestic collateral and repo only`.
- **REQ-003:** define testable candidate `covered-interest-parity-adjusted funding network` against the same opportunities.
- **REQ-004:** report `hedged carry, capacity, FX basis risk and all-in spread` with uncertainty and capacity.
- **NFR-001:** no lookahead; deterministic seed, fixture and versioned parameters.
- **NFR-002:** reject restricted or unlicensed data, live trades and unauthorized actions.
## Acceptance criteria
- **AC-001** REQ-001: correct temporal and eligibility schema on synthetic fixtures.
- **AC-002** REQ-002: baseline cost and constraint tests pass deterministically.
- **AC-003** REQ-003: matched holdout candidate evaluation is reproducible.
- **AC-004** REQ-004: uncertainty, tail cases and net economics are reported.
- **AC-005** NFR-001/002: lookahead and confidentiality checks reject violations.
## Risks, non-goals and falsification
**RISK-001:** false arbitrage from stale asynchronous or inaccessible quotes. **RISK-002:** unobserved transactions, misestimated operating costs or regime instability. No production execution or empirically proven ROI in scope. **Reject H1** if the apparent advantage vanishes after costs, feasible constraints or holdout evaluation. Illustration 2–5× is not verified.
