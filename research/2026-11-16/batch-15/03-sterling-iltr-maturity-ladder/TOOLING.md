# Tooling contracts — Sterling ILTR Auction Demand Smoothing

**Implementation status: proposed; model packages not installed or tested for this project.** The batch contains design documentation and manifests, not an application.

## Reusable Python boundaries

- Target Python 3.11 compatibility; resolve the exact patch and platform at implementation gate G2.
- Propose `httpx` for rights-compliant source retrieval, `pydantic` for the event envelope, `pyarrow`/`polars` for immutable typed columns and UTC as-of replay, `numpy`/`scipy` for clearing-spread intervals, reserve coverage and maturity bucket exposure, and `pytest` plus property-based fixtures for time/units constraints. Selection is a dependency plan, not a current-version recommendation or installed-lock claim.
- Candidate-specific modeling adapter must implement Shape-constrained aggregate supply-curve estimation plus stochastic ladder optimization; evaluate `scipy`/`cvxpy` only where the formulation fits, using MILP-capable solvers for integer variables and documenting solver license, status and tolerances. Statistical models require training-only calibration; no universal solver is assumed to handle all ideas.
- Advanced implementation, if justified: Partially identified robust auction planning over a set of rival-demand curves. Do not add its dependencies before baseline economic value passes.

## Adapter/API contracts

Proposed `load_boe_iltr(as_of, source_manifest, mode) -> EventTable` returns auction x collateral set x release version, time/rights metadata, units and immutable payload hashes. `build_features(events, decision_at) -> FeatureTable` yields clearing-spread intervals, reserve coverage and maturity bucket exposure. `decide(features, limits, costs) -> ResearchDecision` returns auction cash-demand ladder with allocation sensitivity bounds. `evaluate(decisions, outcomes, baseline) -> EvidenceReport` reports GBP funding cost, allocation shortfall, maturity concentration, sensitivity to unobserved demand and bridge usage and rejected cases. No API exists yet; names are future interfaces.

## Pinning and reproducibility gate

Before execution, resolve exact versions in an isolated environment, generate a transitive lock with hashes for Python/platform/solver packages, record timezone database and native BLAS/solver versions, scan licenses, then rebuild from the lock without opportunistic upgrades. Check in the reviewed lock on a separate implementation branch. **Exact pins, dependency compatibility and executable CLI remain BLOCKED.** An invented version list would imply reproducibility that has not been demonstrated.

Public adapters may fetch metadata within provider terms; licensed/private adapters are opt-in and cannot write raw payloads to this public tree. Performance target: Every schedule uses Europe/London DST and verified effective facility calibration; missing auction rule version blocks recommendation.
