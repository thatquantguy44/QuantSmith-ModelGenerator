# TOOLING — Securities Loan Retroactive Rate Amendment Revenue Assurance
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
duckdb, polars, pydantic, hypothesis. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `Global agent lending / US securities loans` market calendar.
- `qmg_core.economics.CostModel`: Value in avoided losses and less manual rework, not trading alpha; false dispute costs and review minutes cap benefit.
- `qmg_core.baselines.PolicyComparator`: Latest agreed fee × end-period balance × elapsed days
- `qmg_core.evals.FalsificationGate`: No improvement in high-severity seeded exceptions relative to deterministic ledger, or unauthorized dispute actions.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/stockloan_rate_amendment_auditor/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: Synthetic loans, amendment lifecycle, dated fee notices, loan terminations, currency and day-count conventions. Main model: Bitemporal finite-state rate and loan lifecycle ledger with invariant checks. Optional next step: Probabilistic anomaly prioritization atop an exact contract-aware billing engine.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
