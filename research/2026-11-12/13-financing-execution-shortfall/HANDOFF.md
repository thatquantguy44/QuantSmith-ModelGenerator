# HANDOFF — Financing Execution Shortfall Model
## State of work
Research design **draft only**. No data ingestion, computation, validation tests, model code, trading adapter, production agent, or positive empirical findings.
**Owner/reviewer:** unassigned.
## Question to validate
Point-in-time causal leakage attribution discovers correctable costs over a quote-only baseline.
**Next authorized action:** verify access and data time conventions for Timestamped RFQs, quotes, fill/rejects, booked fees, market moves and settlement, then implement synthetic fixture and cost-inclusive baseline: executed spread minus indicative quote.
## Primary blockers
- Licensing for licensed executable reference quotes; access to authorized RFQ and transaction lifecycle logs requires separate approvals.
- quotes may be non-executable; client selection creates bias.
- Estimated benefit/cost 2–4× is an unsupported planning assumption pending empirical cost and capacity estimates.
## Reproducibility and provenance
Use immutable data source + as-of timestamp, model/commit hash, seeds, solver tolerance, config, out-of-sample split and economic cost ledger. Preserve failed research results. Do not include raw private/vendor data in this public repository.
