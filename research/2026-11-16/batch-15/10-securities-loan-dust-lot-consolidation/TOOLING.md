# Tooling contracts — Securities-Loan Dust-Lot Consolidation

**Implementation status: proposed; model packages not installed or tested for this project.** The batch contains design documentation and manifests, not an application.

## Reusable Python boundaries

- Target Python 3.11 compatibility; resolve the exact patch and platform at implementation gate G2.
- Propose `httpx` for rights-compliant source retrieval, `pydantic` for the event envelope, `pyarrow`/`polars` for immutable typed columns and UTC as-of replay, `numpy`/`scipy` for fixed servicing charge, permitted owner-lot map and movement-cost matrix, and `pytest` plus property-based fixtures for time/units constraints. Selection is a dependency plan, not a current-version recommendation or installed-lock claim.
- Candidate-specific modeling adapter must implement Fixed-charge transportation MILP; evaluate `scipy`/`cvxpy` only where the formulation fits, using MILP-capable solvers for integer variables and documenting solver license, status and tolerances. Statistical models require training-only calibration; no universal solver is assumed to handle all ideas.
- Advanced implementation, if justified: Multi-period lot consolidation with persistence penalties and uncertain demand bands. Do not add its dependencies before baseline economic value passes.

## Adapter/API contracts

Proposed `load_loan_lots(as_of, source_manifest, mode) -> EventTable` returns owner x borrower x security loan lot x service day, time/rights metadata, units and immutable payload hashes. `build_features(events, decision_at) -> FeatureTable` yields fixed servicing charge, permitted owner-lot map and movement-cost matrix. `decide(features, limits, costs) -> ResearchDecision` returns consolidation suggestions with per-owner exposure/revenue reconciliation. `evaluate(decisions, outcomes, baseline) -> EvidenceReport` reports servicing cost, active lots, net revenue, owner fairness constraints, turnover and time to solve and rejected cases. No API exists yet; names are future interfaces.

## Pinning and reproducibility gate

Before execution, resolve exact versions in an isolated environment, generate a transitive lock with hashes for Python/platform/solver packages, record timezone database and native BLAS/solver versions, scan licenses, then rebuild from the lock without opportunistic upgrades. Check in the reviewed lock on a separate implementation branch. **Exact pins, dependency compatibility and executable CLI remain BLOCKED.** An invented version list would imply reproducibility that has not been demonstrated.

Public adapters may fetch metadata within provider terms; licensed/private adapters are opt-in and cannot write raw payloads to this public tree. Performance target: Deterministic tie-breaking and original-book fallback on infeasibility; quantity and owner revenue reconcile exactly to declared permitted changes.
