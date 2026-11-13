# HANDOFF — Balance-Sheet Seasonality Arbitrage
## State of work
Research design **draft only**. No data ingestion, computation, validation tests, model code, trading adapter, production agent, or positive empirical findings.
**Owner/reviewer:** unassigned.
## Question to validate
Calendar-aware funding reduces ex-ante cost on unseen quarter-ends after realistic balance-sheet charges.
**Next authorized action:** verify access and data time conventions for Repo spread term structure, settlement calendar, quarter-end dates, financing usage, then implement synthetic fixture and cost-inclusive baseline: constant overnight-roll financing.
## Primary blockers
- Licensing for licensed term repo rate and dealer capacity proxies; access to approved internal portfolio-specific capacity cost requires separate approvals.
- well-known quarter-end effects may already be fully priced.
- Estimated benefit/cost 2–4× is an unsupported planning assumption pending empirical cost and capacity estimates.
## Reproducibility and provenance
Use immutable data source + as-of timestamp, model/commit hash, seeds, solver tolerance, config, out-of-sample split and economic cost ledger. Preserve failed research results. Do not include raw private/vendor data in this public repository.
