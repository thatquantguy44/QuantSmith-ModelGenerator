# PLAN — US Bank Deposit Beta and Mark-to-Market Securities Run Risk
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → us-bank-deposit-beta-run-risk normalized state → Uninsured deposit share plus book capital ratio → Hierarchical deposit beta estimation plus accounting-based duration stress → economic replay → invariants + negative controls → independent research review`.

## Data contracts
FDIC bank Call Reports, quarterly uninsured deposits, HTM/AFS loss fields, benchmark rates, bank equity CDS
Record source version, unit, calendar/market timezone and initial public visibility. Quarter-end balances become usable only at the first public Call Report publication, not period end.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Uninsured deposit share plus book capital ratio`; quantify human and market execution capacity honestly.
- Candidate `Hierarchical deposit beta estimation plus accounting-based duration stress` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Agent-based depositor migration with liquidity haircut and contagion sensitivity; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Quarterly revisions, mergers, bank survivorship and missing bank-specific deposit pricing.
- Implementation economics: Large regional bank equity/cash bonds viable; small banks thin, CDS pricing inaccessible and not required for public proxy.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No incremental forecast versus capital/deposit mix baseline after strict public release lag.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
