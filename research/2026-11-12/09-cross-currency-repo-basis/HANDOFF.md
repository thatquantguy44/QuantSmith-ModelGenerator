# HANDOFF — Cross-Currency Repo Basis Optimization
## State of work
Research design **draft only**. No data ingestion, computation, validation tests, model code, trading adapter, production agent, or positive empirical findings.
**Owner/reviewer:** unassigned.
## Question to validate
CIP-adjusted multi-currency routing beats domestic-only financing where transferable collateral exists.
**Next authorized action:** verify access and data time conventions for FX swaps, currencies, tenor rates, haircuts, FX settlements, taxes, legal eligibility, then implement synthetic fixture and cost-inclusive baseline: domestic collateral and repo only.
## Primary blockers
- Licensing for licensed executable FX swap and global repo market data; access to permissioned legal entity funding and collateral rules requires separate approvals.
- false arbitrage from stale asynchronous or inaccessible quotes.
- Estimated benefit/cost 2–5× is an unsupported planning assumption pending empirical cost and capacity estimates.
## Reproducibility and provenance
Use immutable data source + as-of timestamp, model/commit hash, seeds, solver tolerance, config, out-of-sample split and economic cost ledger. Preserve failed research results. Do not include raw private/vendor data in this public repository.
