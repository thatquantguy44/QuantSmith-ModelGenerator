# HANDOFF — Collateral Settlement Failure Propagation
## State of work
Research design **draft only**. No data ingestion, computation, validation tests, model code, trading adapter, production agent, or positive empirical findings.
**Owner/reviewer:** unassigned.
## Question to validate
Network preventive routing reduces aggregate failed obligations relative to isolated fail scoring.
**Next authorized action:** verify access and data time conventions for Dependency-linked settlement legs, legal routes, timestamps, collateral and failed instructions, then implement synthetic fixture and cost-inclusive baseline: FIFO escalation by individual settlement.
## Primary blockers
- Licensing for licensed triparty collateral and settlement standards; access to approved settlement dependency and fail-event logs requires separate approvals.
- incomplete external dependencies and cross-entity visibility.
- Estimated benefit/cost 2–4× is an unsupported planning assumption pending empirical cost and capacity estimates.
## Reproducibility and provenance
Use immutable data source + as-of timestamp, model/commit hash, seeds, solver tolerance, config, out-of-sample split and economic cost ledger. Preserve failed research results. Do not include raw private/vendor data in this public repository.
