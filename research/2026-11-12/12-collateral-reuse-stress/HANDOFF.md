# HANDOFF — Collateral Reuse Chain Stress Testing
## State of work
Research design **draft only**. No data ingestion, computation, validation tests, model code, trading adapter, production agent, or positive empirical findings.
**Owner/reviewer:** unassigned.
## Question to validate
Provenance-aware reuse graph explains stress contractions beyond gross reused collateral.
**Next authorized action:** verify access and data time conventions for Source provenance, permissioned reuse contracts, collateral movements, haircut and margin events, then implement synthetic fixture and cost-inclusive baseline: gross collateral stock and static stress.
## Primary blockers
- Licensing for licensed settlement asset characteristics and market haircuts; access to approved collateral lot provenance and reuse restrictions requires separate approvals.
- double counting and unsupported rehypothecation rights.
- Estimated benefit/cost 1–4× is an unsupported planning assumption pending empirical cost and capacity estimates.
## Reproducibility and provenance
Use immutable data source + as-of timestamp, model/commit hash, seeds, solver tolerance, config, out-of-sample split and economic cost ledger. Preserve failed research results. Do not include raw private/vendor data in this public repository.
