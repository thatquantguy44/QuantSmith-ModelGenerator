# HANDOFF — Auction-Based Securities Lending Liquidity Discovery
## State of work
Research design **draft only**. No data ingestion, computation, validation tests, model code, trading adapter, production agent, or positive empirical findings.
**Owner/reviewer:** unassigned.
## Question to validate
A structural auction policy improves net revenue over highest-fee-first after response and retention costs.
**Next authorized action:** verify access and data time conventions for Timestamped locate quotes, revisions, rejects, fills, quantities and source-specific inventory, then implement synthetic fixture and cost-inclusive baseline: highest-fee-first feasible allocation.
## Primary blockers
- Licensing for licensed securities-lending prices and locate benchmarks; access to approved anonymized desk RFQ/locate/fill histories requires separate approvals.
- censored demand, endogenous quote selection.
- Estimated benefit/cost 3–6× is an unsupported planning assumption pending empirical cost and capacity estimates.
## Reproducibility and provenance
Use immutable data source + as-of timestamp, model/commit hash, seeds, solver tolerance, config, out-of-sample split and economic cost ledger. Preserve failed research results. Do not include raw private/vendor data in this public repository.
