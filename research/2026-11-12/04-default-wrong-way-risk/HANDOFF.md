# HANDOFF — Borrower Default Wrong-Way Risk Optimization
## State of work
Research design **draft only**. No data ingestion, computation, validation tests, model code, trading adapter, production agent, or positive empirical findings.
**Owner/reviewer:** unassigned.
## Question to validate
Joint default-exposure modeling finds stressed loss missed by independent PD/haircut rules.
**Next authorized action:** verify access and data time conventions for Counterparty credit, collateral, contract closeout provisions, stress price and liquidity history, then implement synthetic fixture and cost-inclusive baseline: independent PD times static haircut.
## Primary blockers
- Licensing for licensed historical credit spreads and recovery data; access to authorized indemnity contracts and exposure profiles requires separate approvals.
- sparse default observations and unidentifiable tail parameters.
- Estimated benefit/cost 2–4× is an unsupported planning assumption pending empirical cost and capacity estimates.
## Reproducibility and provenance
Use immutable data source + as-of timestamp, model/commit hash, seeds, solver tolerance, config, out-of-sample split and economic cost ledger. Preserve failed research results. Do not include raw private/vendor data in this public repository.
