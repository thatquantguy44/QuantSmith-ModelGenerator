# HANDOFF — Repo Term Structure Dislocation Engine
## State of work
Research design **draft only**. No data ingestion, computation, validation tests, model code, trading adapter, production agent, or positive empirical findings.
**Owner/reviewer:** unassigned.
## Question to validate
A collateral-aware funding curve beats overnight rolling after executable financing costs.
**Next authorized action:** verify access and data time conventions for Repo rate/tenor quotes, SOFR, collateral CUSIP, haircut, balance-sheet dates, then implement synthetic fixture and cost-inclusive baseline: overnight funding rollover.
## Primary blockers
- Licensing for licensed term-repo dealer axes and securities prices; access to permissioned repo transaction and balance-sheet cost history requires separate approvals.
- indicative prices and bid/ask execution mismatch.
- Estimated benefit/cost 2–5× is an unsupported planning assumption pending empirical cost and capacity estimates.
## Reproducibility and provenance
Use immutable data source + as-of timestamp, model/commit hash, seeds, solver tolerance, config, out-of-sample split and economic cost ledger. Preserve failed research results. Do not include raw private/vendor data in this public repository.
