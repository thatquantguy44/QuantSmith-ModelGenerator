# PLAN — Securities Loan Retroactive Rate Amendment Revenue Assurance
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → stockloan-rate-amendment-auditor normalized state → Latest agreed fee × end-period balance × elapsed days → Bitemporal finite-state rate and loan lifecycle ledger with invariant checks → economic replay → invariants + negative controls → independent research review`.

## Data contracts
Synthetic loans, amendment lifecycle, dated fee notices, loan terminations, currency and day-count conventions
Record source version, unit, calendar/market timezone and initial public visibility. Invoice run includes only fee amendments authorized and received before invoice cut-off, even if effective date is earlier.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Latest agreed fee × end-period balance × elapsed days`; quantify human and market execution capacity honestly.
- Candidate `Bitemporal finite-state rate and loan lifecycle ledger with invariant checks` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Probabilistic anomaly prioritization atop an exact contract-aware billing engine; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Contract-level bilateral waiver rules, fee confirmation ambiguity and out-of-order event feeds.
- Implementation economics: Value in avoided losses and less manual rework, not trading alpha; false dispute costs and review minutes cap benefit.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No improvement in high-severity seeded exceptions relative to deterministic ledger, or unauthorized dispute actions.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
