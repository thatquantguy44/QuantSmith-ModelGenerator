# TOOLING — Tri-Party Repo Margin Dispute Root-Cause and Evidence Classifier
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
pydantic, polars, networkx, spaCy, pytest. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `US and European tri-party collateral` market calendar.
- `qmg_core.economics.CostModel`: Operational capacity limited by manual reviewer; never auto-settle margin on agent output.
- `qmg_core.baselines.PolicyComparator`: FIFO triage by dispute amount and ticket keywords
- `qmg_core.evals.FalsificationGate`: LLM cannot improve verified resolver without hallucinated legal clauses or unacceptable false settlements.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/triparty_margin_dispute_root_cause/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: Synthetic dispute notices, collateral marks, haircut schedules, legal clocks, status and resolution labels. Main model: Deterministic valuation reconciliation then provenance-based root-cause ranking. Optional next step: Constrained language-model document extraction with deterministic verifier and abstain-on-conflict.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
