# HANDOFF — Treasury Specials Relative-Value Network
## State of work
Research design **draft only**. No data ingestion, computation, validation tests, model code, trading adapter, production agent, or positive empirical findings.
**Owner/reviewer:** unassigned.
## Question to validate
A supply-aware graph explains and monetizes relative scarcity after full trading costs.
**Next authorized action:** verify access and data time conventions for CUSIP-level repo and general-collateral rates, SOMA auctions, supply, futures basket, fails, then implement synthetic fixture and cost-inclusive baseline: historical CUSIP z-score of specials.
## Primary blockers
- Licensing for licensed executable special repo quotations; access to approved desk balances and collateral financing trades requires separate approvals.
- public SOMA cannot substitute for executable CUSIP quotes.
- Estimated benefit/cost 2–4× is an unsupported planning assumption pending empirical cost and capacity estimates.
## Reproducibility and provenance
Use immutable data source + as-of timestamp, model/commit hash, seeds, solver tolerance, config, out-of-sample split and economic cost ledger. Preserve failed research results. Do not include raw private/vendor data in this public repository.
