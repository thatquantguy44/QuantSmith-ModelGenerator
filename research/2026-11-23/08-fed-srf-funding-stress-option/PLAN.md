# PLAN — Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → fed-srf-funding-stress-option normalized state → SOFR-GC spread threshold with no SRF information → Event-conditioned calibrated logistic hazard with lag-safe publication ledger → economic replay → invariants + negative controls → independent research review`.

## Data contracts
Official SRF accepted/submitted quantities, summary rates, SOFR, OFR cleared/triparty repo aggregates
Record source version, unit, calendar/market timezone and initial public visibility. Use posted operation result time and repo series 1-2-day publication lags; do not use same-day hidden participant-level bids.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `SOFR-GC spread threshold with no SRF information`; quantify human and market execution capacity honestly.
- Candidate `Event-conditioned calibrated logistic hazard with lag-safe publication ledger` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Structural real-option exercise mapping latent facility usage and dealer cash constraints; justify its added parameters and risks through a paired ablation.
- Critical identification concern: SRF operational parameter changes, known policy regime shifts, lack of entity-level same-day data.
- Implementation economics: Research output is risk-monitoring, not direct trading opportunity; facility eligibility and costs differ by participant.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** No holdout information gain after timing correction, or false positives overwhelm funding buffer costs.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
