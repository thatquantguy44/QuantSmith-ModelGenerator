# PLAN — Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → agency-mbs-dollar-roll-delivery-option normalized state → Dollar-roll implied financing vs same-tenor generic repo without delivery-option valuation → Constrained pool-delivery optimizer with observable pool financing carry and roll prices → economic replay → invariants + negative controls → independent research review`.

## Data contracts
TBA front/back prices, pools, payups, coupon schedules, specified-pool risk, MBSD netting, EPN eligibility and execution costs
Record source version, unit, calendar/market timezone and initial public visibility. Decision at pre-roll executable quote; EPN pool assignment becomes known later and must not leak into earlier signals.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Dollar-roll implied financing vs same-tenor generic repo without delivery-option valuation`; quantify human and market execution capacity honestly.
- Candidate `Constrained pool-delivery optimizer with observable pool financing carry and roll prices` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Stochastic pool quality and delivery-selection real-options game with cheapest-deliverable simulation; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Pool price selection, payup optionality, actual pool availability and post-trade EPN leakage.
- Implementation economics: Market depth and eligible pool inventory limit size; include bid/ask, delivery allocations, financing and clearing margin.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No stable out-of-sample cost-adjusted advantage over delivery-aware manual baseline at realistic pool eligibility.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
