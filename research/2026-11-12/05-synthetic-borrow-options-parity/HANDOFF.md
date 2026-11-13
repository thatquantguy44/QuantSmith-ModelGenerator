# HANDOFF — Synthetic Borrow Supply via Options Parity
## State of work
Research design **draft only**. No data ingestion, computation, validation tests, model code, trading adapter, production agent, or positive empirical findings.
**Owner/reviewer:** unassigned.
## Question to validate
Parity-adjusted replication reduces funding cost for eligible positions after dividends and exercise risk.
**Next authorized action:** verify access and data time conventions for Options bid/ask, dividends, loan fees, stock price, funding, margin and assignment mechanics, then implement synthetic fixture and cost-inclusive baseline: physical borrow only.
## Primary blockers
- Licensing for licensed options depth and securities-loan fees; access to approved stock-loan quote/locate history requires separate approvals.
- American exercise and forecast-dividend mismatch.
- Estimated benefit/cost 2–5× is an unsupported planning assumption pending empirical cost and capacity estimates.
## Reproducibility and provenance
Use immutable data source + as-of timestamp, model/commit hash, seeds, solver tolerance, config, out-of-sample split and economic cost ledger. Preserve failed research results. Do not include raw private/vendor data in this public repository.
