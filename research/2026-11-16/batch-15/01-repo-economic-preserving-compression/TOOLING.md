# Tooling contracts — Repo Compression with Cash-Flow Preservation

**Implementation status: proposed; model packages not installed or tested for this project.** The batch contains design documentation and manifests, not an application.

## Reusable Python boundaries

- Target Python 3.11 compatibility; resolve the exact patch and platform at implementation gate G2.
- Propose `httpx` for rights-compliant source retrieval, `pydantic` for the event envelope, `pyarrow`/`polars` for immutable typed columns and UTC as-of replay, `numpy`/`scipy` for dated incidence matrices, lot constraints and consent mask, and `pytest` plus property-based fixtures for time/units constraints. Selection is a dependency plan, not a current-version recommendation or installed-lock claim.
- Candidate-specific modeling adapter must implement Mixed-integer minimum-cost circulation with exact cash-flow conservation; evaluate `scipy`/`cvxpy` only where the formulation fits, using MILP-capable solvers for integer variables and documenting solver license, status and tolerances. Statistical models require training-only calibration; no universal solver is assumed to handle all ideas.
- Advanced implementation, if justified: Robust multi-period compression with consent uncertainty and settlement-feasibility cuts. Do not add its dependencies before baseline economic value passes.

## Adapter/API contracts

Proposed `load_repo_ledger(as_of, source_manifest, mode) -> EventTable` returns repo ticket and dated cash/security obligation, time/rights metadata, units and immutable payload hashes. `build_features(events, decision_at) -> FeatureTable` yields dated incidence matrices, lot constraints and consent mask. `decide(features, limits, costs) -> ResearchDecision` returns proposed tear-up/resizing schedule, exact flow certificate and rejected-action reasons. `evaluate(decisions, outcomes, baseline) -> EvidenceReport` reports gross reduction, message reduction, all-in cost, maximum flow residual, consent acceptance and solve time and rejected cases. No API exists yet; names are future interfaces.

## Pinning and reproducibility gate

Before execution, resolve exact versions in an isolated environment, generate a transitive lock with hashes for Python/platform/solver packages, record timezone database and native BLAS/solver versions, scan licenses, then rebuild from the lock without opportunistic upgrades. Check in the reviewed lock on a separate implementation branch. **Exact pins, dependency compatibility and executable CLI remain BLOCKED.** An invented version list would imply reproducibility that has not been demonstrated.

Public adapters may fetch metadata within provider terms; licensed/private adapters are opt-in and cannot write raw payloads to this public tree. Performance target: For a proposed 5,000-ticket set, target p95 solve time <=60 seconds and exact conservation certificate; infeasible or timed-out solves return original book.
