# PLAN — Tri-Party Repo Margin Dispute Root-Cause and Evidence Classifier
**Status: proposed implementation architecture; not executed.**

## Research system
`legal-source-allowlist → release-version capture → triparty-margin-dispute-root-cause normalized state → FIFO triage by dispute amount and ticket keywords → Deterministic valuation reconciliation then provenance-based root-cause ranking → economic replay → invariants + negative controls → independent research review`.

## Data contracts
Synthetic dispute notices, collateral marks, haircut schedules, legal clocks, status and resolution labels
Record source version, unit, calendar/market timezone and initial public visibility. Use values known to both parties at agreed margin timestamp; never use later corrected marks to excuse earlier action.
Build synthetic datasets exercising both ordinary and adversarial cases before attempting licensed ingestion.

## Identification and modeling
- Start with `FIFO triage by dispute amount and ticket keywords`; quantify human and market execution capacity honestly.
- Candidate `Deterministic valuation reconciliation then provenance-based root-cause ranking` is estimated on predeclared training windows and evaluated only after hyperparameters frozen.
- Conditional advanced extension: Constrained language-model document extraction with deterministic verifier and abstain-on-conflict; justify its added parameters and risks through a paired ablation.
- Critical identification concern: Conflicting vendor marks, jurisdiction-specific terms, privacy and LLM overconfidence.
- Implementation economics: Operational capacity limited by manual reviewer; never auto-settle margin on agent output.

## Interfaces (proposed, not present)
`source.load(license,as_of)`, `contract.normalize(records,clock)`, `baseline.solve(states)`, `candidate.solve(states)`, `econ.replay(actions,quotes)`, `evals.falsify()`.
Use the same eligible universe and cost model for both actions, preserve rejection/failure traces, and prohibit false retrospective model availability.

## Requirement/task traceability
REQ-001→T-01,T-02; REQ-002→T-03; REQ-003→T-04,T-05; REQ-004→T-06; NFR-001/NFR-002→T-02,T-07.
**Decision gate:** LLM cannot improve verified resolver without hallucinated legal clauses or unacceptable false settlements.
The implementation is BLOCKED until source rights, timestamps and economic costs are accepted.
