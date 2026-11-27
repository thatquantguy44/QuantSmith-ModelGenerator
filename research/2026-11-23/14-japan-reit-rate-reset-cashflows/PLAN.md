# PLAN — Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → japan-reit-rate-reset-cashflows normalized state → Market REIT index duration and price-to-NAV score → Disclosure-derived maturity-wall factor with event-based hedged return regressions → economic replay → invariants + negative controls → independent research review`.

## Data contracts
BOJ rate time series, J-REIT bond/debt disclosures, rent index, total returns and market-based NAV
Record source version, unit, calendar/market timezone and initial public visibility. Use release/filing acceptance before BOJ event and timestamp debt disclosure versions.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Market REIT index duration and price-to-NAV score`; quantify human and market execution capacity honestly.
- Candidate `Disclosure-derived maturity-wall factor with event-based hedged return regressions` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Tenant lease rollover and financing reset structural cash-flow model; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Japanese disclosure translation/lease renewal timing and selective REIT survivorship.
- Implementation economics: J-REIT constituent liquidity, FX hedge and foreign-investor restrictions limit realized capacity.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No incremental post-rate-shift forecast after issuer fixed-effects and NAV-duration controls.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
