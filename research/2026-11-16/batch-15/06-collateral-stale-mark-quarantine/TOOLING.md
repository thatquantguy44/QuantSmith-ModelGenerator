# Tooling contracts — Collateral Stale-Mark Quarantine and Conservative Valuation

**Implementation status: proposed; model packages not installed or tested for this project.** The batch contains design documentation and manifests, not an application.

## Reusable Python boundaries

- Target Python 3.11 compatibility; resolve the exact patch and platform at implementation gate G2.
- Propose `httpx` for rights-compliant source retrieval, `pydantic` for the event envelope, `pyarrow`/`polars` for immutable typed columns and UTC as-of replay, `numpy`/`scipy` for source age, price convention residual, lineage overlap and conservative interval, and `pytest` plus property-based fixtures for time/units constraints. Selection is a dependency plan, not a current-version recommendation or installed-lock claim.
- Candidate-specific modeling adapter must implement Robust cross-source median and asset-specific age/interval rule; evaluate `scipy`/`cvxpy` only where the formulation fits, using MILP-capable solvers for integer variables and documenting solver license, status and tolerances. Statistical models require training-only calibration; no universal solver is assumed to handle all ideas.
- Advanced implementation, if justified: State-space price filtering with conformal lower valuation bounds and selective quarantine. Do not add its dependencies before baseline economic value passes.

## Adapter/API contracts

Proposed `load_collateral_marks(as_of, source_manifest, mode) -> EventTable` returns collateral instrument x mark source x quote/receive event, time/rights metadata, units and immutable payload hashes. `build_features(events, decision_at) -> FeatureTable` yields source age, price convention residual, lineage overlap and conservative interval. `decide(features, limits, costs) -> ResearchDecision` returns mark status, safe monitoring valuation, lineage warning and escalation reason. `evaluate(decisions, outcomes, baseline) -> EvidenceReport` reports value shortfall, interval coverage, false positives, stale detection delay, desk override rate and review hours and rejected cases. No API exists yet; names are future interfaces.

## Pinning and reproducibility gate

Before execution, resolve exact versions in an isolated environment, generate a transitive lock with hashes for Python/platform/solver packages, record timezone database and native BLAS/solver versions, scan licenses, then rebuild from the lock without opportunistic upgrades. Check in the reviewed lock on a separate implementation branch. **Exact pins, dependency compatibility and executable CLI remain BLOCKED.** An invented version list would imply reproducibility that has not been demonstrated.

Public adapters may fetch metadata within provider terms; licensed/private adapters are opt-in and cannot write raw payloads to this public tree. Performance target: Target p99 <=100ms per 1,000-mark batch excluding upstream network; missing currency/convention hard-fails. Keep original marks immutable.
