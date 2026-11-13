# HANDOFF — Loan Recall Early-Exercise Boundary
## State of work
Research design **draft only**. No data ingestion, computation, validation tests, model code, trading adapter, production agent, or positive empirical findings.
**Owner/reviewer:** unassigned.
## Question to validate
Owner-specific early-exercise states predict recall timing and lower replacement exposure.
**Next authorized action:** verify access and data time conventions for Loan age, fee, recalls, corporate action calendar, owner restrictions, replacement cost, then implement synthetic fixture and cost-inclusive baseline: constant owner-specific recall probability.
## Primary blockers
- Licensing for licensed proxy calendar, ownership and corporate-event data; access to owner-approved recall and loan history requires separate approvals.
- governance and fiduciary rights cannot be traded away.
- Estimated benefit/cost 2–4× is an unsupported planning assumption pending empirical cost and capacity estimates.
## Reproducibility and provenance
Use immutable data source + as-of timestamp, model/commit hash, seeds, solver tolerance, config, out-of-sample split and economic cost ledger. Preserve failed research results. Do not include raw private/vendor data in this public repository.
