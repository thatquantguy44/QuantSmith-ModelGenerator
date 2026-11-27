# PLAN — Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → lcr-nsfr-secured-funding-shadow-price normalized state → Rank repo offers by quoted rate subject to gross notional limits → Linear/mixed-integer secured funding allocation with LCR/NSFR dual-price attribution → economic replay → invariants + negative controls → independent research review`.

## Data contracts
Public Basel ratio methodology/aggregate trends, synthetic collateral classes, cashflow ladder and legal-entity matrices
Record source version, unit, calendar/market timezone and initial public visibility. Regulatory rule version, haircut classification and reporting entity apply as of funding decision.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Rank repo offers by quoted rate subject to gross notional limits`; quantify human and market execution capacity honestly.
- Candidate `Linear/mixed-integer secured funding allocation with LCR/NSFR dual-price attribution` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Scenario-based shadow-price frontier with intraday and quarter-end liquidity risk; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Entity-specific regulatory implementation and internal forecasts differ; cannot reconstruct actual LCR from public totals.
- Implementation economics: Use only approved internal regulatory measures when available; funding choices constrained by entity/collateral eligibility.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No cost difference over conservative liquidity-constrained benchmark or unstable/uninterpretable duals.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
