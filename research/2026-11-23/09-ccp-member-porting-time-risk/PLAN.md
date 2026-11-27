# PLAN — CCP Member Default Position-Porting Time and Liquidity Optimization
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → ccp-member-porting-time-risk normalized state → Manual first-available eligible clearing member routing → Multi-period mixed-integer stochastic porting/survival flow simulator → economic replay → invariants + negative controls → independent research review`.

## Data contracts
Public CCP rulebooks; synthetic position/eligibility and margin profiles; simulated member outage
Record source version, unit, calendar/market timezone and initial public visibility. Use rule versions effective on default scenario date, exclude assumptions from later CCP notices.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `Manual first-available eligible clearing member routing`; quantify human and market execution capacity honestly.
- Candidate `Multi-period mixed-integer stochastic porting/survival flow simulator` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Distributionally robust queueing network with correlated member liquidity and stress haircuts; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Actual CCP porting legality and bilateral customer consents unknown, correlated failures may be unidentifiable.
- Implementation economics: Not a deployable CCP recovery plan; scenario policy must be vetted by legal and risk.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No improvement in adverse default scenarios over conservative porting alternatives or reliance on forbidden client position data.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
