# PLAN — Chile–Peru Copper Royalty Shock to Sovereign and Mining Credit
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → latam-copper-royalty-credit normalized state → Copper price beta plus sovereign spread changes → Event study with cross-sectional mine exposure and staggered law timing → economic replay → invariants + negative controls → independent research review`.

## Data contracts
USGS production, government royalty statutes, country budgets, company annual filings, credit spreads and currency
Record source version, unit, calendar/market timezone and initial public visibility. Policy event recognized at official publication/enactment time; annual USGS data only upon issuance.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Copper price beta plus sovereign spread changes`; quantify human and market execution capacity honestly.
- Candidate `Event study with cross-sectional mine exposure and staggered law timing` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Partial equilibrium mine-option tax model under investment deferral and country sovereign budget feedback; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Anticipatory legislative pricing, issuer/sov high correlations, illiquid local bond prices.
- Implementation economics: Bid/ask for mining credits and FX may swamp basis; avoid assuming continuous trading around policy announcements.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No holdout effect after commodity beta and country shock controls or cannot identify legal effective date.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
