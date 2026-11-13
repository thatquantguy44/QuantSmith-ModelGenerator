# HANDOFF — Intraday Collateral Liquidity Forecasting via Queueing Theory
## State of work
Research design **draft only**. No data ingestion, computation, validation tests, model code, trading adapter, production agent, or positive empirical findings.
**Owner/reviewer:** unassigned.
## Question to validate
Queue-aware controls lower buffer expense without increasing missed margin deadlines.
**Next authorized action:** verify access and data time conventions for Intraday margin calls, settlement timestamps, queue lengths, cash/collateral buffers, fails, then implement synthetic fixture and cost-inclusive baseline: fixed intraday liquidity reserve.
## Primary blockers
- Licensing for licensed intraday money-market pricing; access to approved margin and settlement event logs requires separate approvals.
- timestamp quality and hidden queue-priority rules.
- Estimated benefit/cost 3–5× is an unsupported planning assumption pending empirical cost and capacity estimates.
## Reproducibility and provenance
Use immutable data source + as-of timestamp, model/commit hash, seeds, solver tolerance, config, out-of-sample split and economic cost ledger. Preserve failed research results. Do not include raw private/vendor data in this public repository.
