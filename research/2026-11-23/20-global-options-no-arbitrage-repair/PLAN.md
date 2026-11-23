# PLAN — Arbitrage-Free Equity Volatility Surface Repair Across Markets
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → global-options-no-arbitrage-repair normalized state → Per-expiry unconstrained cubic interpolation with clip to bid/ask → Static no-arbitrage SVI/SSVI constrained calibration with conservative quote filters → economic replay → invariants + negative controls → independent research review`.

## Data contracts
Time-synchronized option bid/ask, underlying forwards, dividends, exchange calendars, corporate action adjustments
Record source version, unit, calendar/market timezone and initial public visibility. Quote timestamp aligned to each exchange session; repair uses no quotes from future or closed-market snapshots.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Per-expiry unconstrained cubic interpolation with clip to bid/ask`; quantify human and market execution capacity honestly.
- Candidate `Static no-arbitrage SVI/SSVI constrained calibration with conservative quote filters` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Joint multi-market neural stochastic volatility calibrated to arbitrage constraints and holidays; justify its added parameters and risks through a paired ablation.
- Critical identification concern: American vs European option styles, dividend marks, early exercise, restricted historical quote rights.
- Implementation economics: Surface repairs support quality/risk decisions first; apparent arbitrage cannot be traded without depth and cost.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** Constrained repair does not reduce out-of-sample pricing/hedging error or introduces hidden quote crossings.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
