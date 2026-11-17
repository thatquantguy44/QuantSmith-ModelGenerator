# Tooling contracts — Owner Co-Withdrawal Limits for Lendable Inventory

**Implementation status: proposed; model packages not installed or tested for this project.** The batch contains design documentation and manifests, not an application.

## Reusable Python boundaries

- Target Python 3.11 compatibility; resolve the exact patch and platform at implementation gate G2.
- Propose `httpx` for rights-compliant source retrieval, `pydantic` for the event envelope, `pyarrow`/`polars` for immutable typed columns and UTC as-of replay, `numpy`/`scipy` for common withdrawal factor, owner lineage groups and replacement tail scenarios, and `pytest` plus property-based fixtures for time/units constraints. Selection is a dependency plan, not a current-version recommendation or installed-lock claim.
- Candidate-specific modeling adapter must implement Hierarchical common-factor withdrawal model and CVaR allocation; evaluate `scipy`/`cvxpy` only where the formulation fits, using MILP-capable solvers for integer variables and documenting solver license, status and tolerances. Statistical models require training-only calibration; no universal solver is assumed to handle all ideas.
- Advanced implementation, if justified: Distributionally robust copula stress allocation with mandate-group shocks. Do not add its dependencies before baseline economic value passes.

## Adapter/API contracts

Proposed `load_owner_inventory(as_of, source_manifest, mode) -> EventTable` returns owner x security x dated available-inventory snapshot, time/rights metadata, units and immutable payload hashes. `build_features(events, decision_at) -> FeatureTable` yields common withdrawal factor, owner lineage groups and replacement tail scenarios. `decide(features, limits, costs) -> ResearchDecision` returns source concentration limits and joint-withdrawal stress certificate. `evaluate(decisions, outcomes, baseline) -> EvidenceReport` reports tail replacement cost, simultaneous-shortfall calibration, revenue retained, stress coverage and concentration and rejected cases. No API exists yet; names are future interfaces.

## Pinning and reproducibility gate

Before execution, resolve exact versions in an isolated environment, generate a transitive lock with hashes for Python/platform/solver packages, record timezone database and native BLAS/solver versions, scan licenses, then rebuild from the lock without opportunistic upgrades. Check in the reviewed lock on a separate implementation branch. **Exact pins, dependency compatibility and executable CLI remain BLOCKED.** An invented version list would imply reproducibility that has not been demonstrated.

Public adapters may fetch metadata within provider terms; licensed/private adapters are opt-in and cannot write raw payloads to this public tree. Performance target: No raw owner identity or positions in public artifacts; a private run must use pseudonymous IDs and lineage access controls.
