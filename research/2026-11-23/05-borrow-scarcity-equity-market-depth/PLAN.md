# PLAN — Borrow Scarcity Causal Effect on Equity Market-Maker Quoted Depth
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → borrow-scarcity-equity-market-depth normalized state → Spread/depth forecasting using only realized volatility and market cap → Matched differences-in-differences/event-time instrumental analysis → economic replay → invariants + negative controls → independent research review`.

## Data contracts
Borrow availability and fees, market quotes/trades, issuer event calendars and exclusion instruments
Record source version, unit, calendar/market timezone and initial public visibility. Quote-decision timing after actual supply notice; event timestamps distinguish pre-event leak, regular session and close.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Spread/depth forecasting using only realized volatility and market cap`; quantify human and market execution capacity honestly.
- Candidate `Matched differences-in-differences/event-time instrumental analysis` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Structural market-maker inventory equilibrium with dynamic borrowing constraint; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Selection on distressed shorts, simultaneous volatility and hard-to-borrow endogenous events.
- Implementation economics: Not an unconditional trading signal; capacity depends on quote depth and borrow clearance, include adverse selection.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No pre-registered effect with valid pretrends/instruments or effect only on illiquid untradeable names.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
