# PLAN — European Interconnector Congestion Power-Spread State Estimator
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → europe-power-congestion-spreads normalized state → Historical seasonal hourly spread by zone pair → Physical-congestion regime HMM with capacity-constrained exposure mapper → economic replay → invariants + negative controls → independent research review`.

## Data contracts
ENTSO-E day-ahead prices, transfer capacities, interconnector outages, wind/load forecasts and contract liquidity
Record source version, unit, calendar/market timezone and initial public visibility. Only ENTSO-E forecasts published before day-ahead bidding deadline; actual flows/prices are evaluation targets.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Historical seasonal hourly spread by zone pair`; quantify human and market execution capacity honestly.
- Candidate `Physical-congestion regime HMM with capacity-constrained exposure mapper` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Stochastic DC power flow and multi-region graph forecasts with out-of-area transfer shadow prices; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Cross-zone transmission rights and operational capacities not freely tradable; timestamps and price revisions.
- Implementation economics: Transmission rights/market access and collateral requirements dominate quoted spread opportunities.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** Spread gains disappear after simultaneous public forecast access, congestion settlement and capacity rights.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
