# Tooling contracts — India Bond Index-Flow Saturation

**Implementation status: proposed; model packages not installed or tested for this project.** The batch contains design documentation and manifests, not an application.

## Reusable Python boundaries

- Target Python 3.11 compatibility; resolve the exact patch and platform at implementation gate G2.
- Propose `httpx` for rights-compliant source retrieval, `pydantic` for the event envelope, `pyarrow`/`polars` for immutable typed columns and UTC as-of replay, `numpy`/`scipy` for announced flow pressure, free-float turnover and lagged foreign ownership saturation, and `pytest` plus property-based fixtures for time/units constraints. Selection is a dependency plan, not a current-version recommendation or installed-lock claim.
- Candidate-specific modeling adapter must implement Matched staggered event study with demand-pressure interactions; evaluate `scipy`/`cvxpy` only where the formulation fits, using MILP-capable solvers for integer variables and documenting solver license, status and tolerances. Statistical models require training-only calibration; no universal solver is assumed to handle all ideas.
- Advanced implementation, if justified: Doubly robust event design plus a structural price-impact saturation curve. Do not add its dependencies before baseline economic value passes.

## Adapter/API contracts

Proposed `load_india_index_events(as_of, source_manifest, mode) -> EventTable` returns government bond x announcement/rebalance cohort x public flow release, time/rights metadata, units and immutable payload hashes. `build_features(events, decision_at) -> FeatureTable` yields announced flow pressure, free-float turnover and lagged foreign ownership saturation. `decide(features, limits, costs) -> ResearchDecision` returns event-study estimands, placebo diagnostics and duration-neutral research basket. `evaluate(decisions, outcomes, baseline) -> EvidenceReport` reports net residual bps, pretrend diagnostics, placebo effects, DV01 neutrality, turnover and sensitivity to AUM bounds and rejected cases. No API exists yet; names are future interfaces.

## Pinning and reproducibility gate

Before execution, resolve exact versions in an isolated environment, generate a transitive lock with hashes for Python/platform/solver packages, record timezone database and native BLAS/solver versions, scan licenses, then rebuild from the lock without opportunistic upgrades. Check in the reviewed lock on a separate implementation branch. **Exact pins, dependency compatibility and executable CLI remain BLOCKED.** An invented version list would imply reproducibility that has not been demonstrated.

Public adapters may fetch metadata within provider terms; licensed/private adapters are opt-in and cannot write raw payloads to this public tree. Performance target: Announced and effective membership must occupy separate columns; unknown original announcement time blocks that cohort.
