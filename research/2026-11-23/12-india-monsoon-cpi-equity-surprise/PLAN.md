# PLAN — India Monsoon Surprise to Food CPI and Local Equity Pricing
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → india-monsoon-cpi-equity-surprise normalized state → All-India seasonal rainfall deviation plus autoregressive food CPI → Hierarchical spatial distributed-lag regression + causal crop weighting → economic replay → invariants + negative controls → independent research review`.

## Data contracts
IMD daily district rain, crop sowing weights, RBI CPI release, state-level harvest, NSE sector returns
Record source version, unit, calendar/market timezone and initial public visibility. IMD publication timestamp and next-tradable-session; CPI only after official release, no revisions used retroactively.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `All-India seasonal rainfall deviation plus autoregressive food CPI`; quantify human and market execution capacity honestly.
- Candidate `Hierarchical spatial distributed-lag regression + causal crop weighting` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Weather-to-crop graph structural state-space model with uncertainty propagation; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Historical IMD OGD resources lag, crop mix revisions, rainfall not yield and policy interventions.
- Implementation economics: Large liquid Indian stocks capacity feasible only with correct foreign-investor access, FX costs and exchange calendars.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No incremental holdout inflation forecast or stock-return effect against rainfall benchmark.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
