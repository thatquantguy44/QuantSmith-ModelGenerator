# PLAN — Corporate Bond Securities Lending from CDS Basis Hedge Demand
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → corporate-bond-cds-basis-borrow-demand normalized state → Trailing borrower request count and issue-size utilization → Matched event study plus borrow-arrival hazard conditional on CDS-bond basis → economic replay → invariants + negative controls → independent research review`.

## Data contracts
CUSIP-level corporate bond lending fees/locates, CDS curves, TRACE trade activity, issue amount, corporate actions
Record source version, unit, calendar/market timezone and initial public visibility. CDS and cash-bond spreads only after published executable quote times; lending fills observed subsequently.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Trailing borrower request count and issue-size utilization`; quantify human and market execution capacity honestly.
- Candidate `Matched event study plus borrow-arrival hazard conditional on CDS-bond basis` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Structural joint CDS/bond market-maker inventory model with selection-corrected demand; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Non-executable CDS quotes, bond TRACE delay and endogeneity of credit distress.
- Implementation economics: Bond borrow capacity and transaction costs can overwhelm narrow basis; never equate public volume with tradable borrow.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** Estimated basis effects fail paired holdouts or increase rejected locates after slippage and liquidity controls.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
