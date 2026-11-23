# PLAN — Biotech FDA Catalyst Probability versus Options Event Premium
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → biotech-fda-event-variance-premium normalized state → Historical absolute event returns grouped by market cap and indication → Regulatory-document event taxonomy + shrinkage conditional jump model → economic replay → invariants + negative controls → independent research review`.

## Data contracts
FDA event dates, approval histories, pre-event public filings, full options surfaces, equity halt and event-time trades
Record source version, unit, calendar/market timezone and initial public visibility. No use of FDA outcome until public approval announcement; option quotes at last feasible pre-event time.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Historical absolute event returns grouped by market cap and indication`; quantify human and market execution capacity honestly.
- Candidate `Regulatory-document event taxonomy + shrinkage conditional jump model` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Hierarchical Bayesian decision-state model and option-neutral density decomposition; justify its added parameters and risks through a paired ablation.
- Critical identification concern: FDA database daily updates can lag original approval; sample selection, delistings and halted option quotes.
- Implementation economics: Biotech option spreads and gap risk severe; define small budget and loss limit before evaluating.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** Conditional probability model fails event-matched calibration or net executable option premium.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
