# Tooling contracts — US Municipal Call-Exercise Friction Surface

**Implementation status: proposed; model packages not installed or tested for this project.** The batch contains design documentation and manifests, not an application.

## Reusable Python boundaries

- Target Python 3.11 compatibility; resolve the exact patch and platform at implementation gate G2.
- Propose `httpx` for rights-compliant source retrieval, `pydantic` for the event envelope, `pyarrow`/`polars` for immutable typed columns and UTC as-of replay, `numpy`/`scipy` for refunding incentive, notice state, issuer friction and time-to-call, and `pytest` plus property-based fixtures for time/units constraints. Selection is a dependency plan, not a current-version recommendation or installed-lock claim.
- Candidate-specific modeling adapter must implement Discrete-time survival model with economic refunding covariates; evaluate `scipy`/`cvxpy` only where the formulation fits, using MILP-capable solvers for integer variables and documenting solver license, status and tolerances. Statistical models require training-only calibration; no universal solver is assumed to handle all ideas.
- Advanced implementation, if justified: Hierarchical issuer stopping model with financing frictions and cash-flow scenario valuation. Do not add its dependencies before baseline economic value passes.

## Adapter/API contracts

Proposed `load_muni_call_disclosures(as_of, source_manifest, mode) -> EventTable` returns bond x call opportunity x public notice/financial filing event, time/rights metadata, units and immutable payload hashes. `build_features(events, decision_at) -> FeatureTable` yields refunding incentive, notice state, issuer friction and time-to-call. `decide(features, limits, costs) -> ResearchDecision` returns call probability surface, cash-flow distribution and duration-matched selection report. `evaluate(decisions, outcomes, baseline) -> EvidenceReport` reports Brier score, cash-flow MAE, duration error, net matched return, spread/size sensitivity and call calibration and rejected cases. No API exists yet; names are future interfaces.

## Pinning and reproducibility gate

Before execution, resolve exact versions in an isolated environment, generate a transitive lock with hashes for Python/platform/solver packages, record timezone database and native BLAS/solver versions, scan licenses, then rebuild from the lock without opportunistic upgrades. Check in the reviewed lock on a separate implementation branch. **Exact pins, dependency compatibility and executable CLI remain BLOCKED.** An invented version list would imply reproducibility that has not been demonstrated.

Public adapters may fetch metadata within provider terms; licensed/private adapters are opt-in and cannot write raw payloads to this public tree. Performance target: Every parsed call term needs a document page/span; conflicting extraordinary versus optional redemption clauses block valuation.
