# PLAN — Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → lending-rebate-floor-optionalities normalized state → Static contractual rebate minus benchmark with no optionality → Rate-tree floor valuation and curve calibration with contract clause parser → economic replay → invariants + negative controls → independent research review`.

## Data contracts
Historical overnight benchmarks, collateral currency curves, cash balances, contract rebate-floor clauses
Record source version, unit, calendar/market timezone and initial public visibility. Valuation at contract initiation using curve observed by quote cut-off, not future realized policy rates.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Static contractual rebate minus benchmark with no optionality`; quantify human and market execution capacity honestly.
- Candidate `Rate-tree floor valuation and curve calibration with contract clause parser` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Multi-currency short-rate stochastic volatility and correlated collateral run-off scenario valuation; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Floor rights and term structures vary by legal agreement; historic negative-rate regimes have sample limitations.
- Implementation economics: Profit only if floors contractually negotiated; hedge notional and floor illiquidity restrict scale.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** Valuation adds no meaningful incremental pricing accuracy to conservative quoted-fee schedules.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
