# PLAN — Sovereign DSA Rating Migration Event Pricing for Frontier Bonds
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → frontier-dsa-rating-migration normalized state → Latest public debt-to-GDP and reserves ratio → Multi-state ordinal risk migration model with publication-aligned survival validation → economic replay → invariants + negative controls → independent research review`.

## Data contracts
Country IMF/World Bank public DSA documents, sovereign events, IMF debt statistics, bond quotes and GDP vintages
Record source version, unit, calendar/market timezone and initial public visibility. Country report posting time and rating applicability; embargo unpublished staff papers and revisions.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Latest public debt-to-GDP and reserves ratio`; quantify human and market execution capacity honestly.
- Candidate `Multi-state ordinal risk migration model with publication-aligned survival validation` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Bayesian sovereign hazard with IMF policy intervention and restructuring recovery scenarios; justify its added parameters and risks through a paired ablation.
- Critical identification concern: DSA coverage selection and program endogeneity, non-tradable distressed bonds, rare default events.
- Implementation economics: Frontier bond sizes/spreads can defeat excess returns; focus risk-control research first.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No improvement over conservative sovereign ratings baseline, or price move entirely before public timestamp.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
