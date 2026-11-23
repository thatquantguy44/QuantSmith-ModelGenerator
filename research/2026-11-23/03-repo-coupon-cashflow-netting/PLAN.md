# PLAN — Repo Coupon and Principal Event Cash-Flow Netting Scheduler
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → repo-coupon-cashflow-netting normalized state → Gross independent payment processing with static buffer → Mixed-integer liquidity scheduling with eligibility/netting-set constraints → economic replay → invariants + negative controls → independent research review`.

## Data contracts
Public bond schedules, ex-coupon dates, settlement calendars, synthetic counterparties and netting agreements
Record source version, unit, calendar/market timezone and initial public visibility. Coupon schedule published at issuance; adjustments and confirmed obligations only after contract notice timestamp.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Gross independent payment processing with static buffer`; quantify human and market execution capacity honestly.
- Candidate `Mixed-integer liquidity scheduling with eligibility/netting-set constraints` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Stochastic event-flow MPC with missed payment penalties and legal-entity netting restrictions; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Wrong beneficial-ownership treatment, netting rights and special cash settlement terms.
- Implementation economics: Savings limited to payments legally eligible for netting; reconciliation costs, daylight overdraft fees and solver latency included.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No capacity-adjusted cost reduction versus pre-netted conventional operations or violations of payment rights.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
