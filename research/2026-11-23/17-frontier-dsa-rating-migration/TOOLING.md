# TOOLING — Sovereign DSA Rating Migration Event Pricing for Frontier Bonds
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
lifelines, pymc, statsmodels, pandas. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `Frontier Africa and select emerging Asia sovereign USD credit` market calendar.
- `qmg_core.economics.CostModel`: Frontier bond sizes/spreads can defeat excess returns; focus risk-control research first.
- `qmg_core.baselines.PolicyComparator`: Latest public debt-to-GDP and reserves ratio
- `qmg_core.evals.FalsificationGate`: No improvement over conservative sovereign ratings baseline, or price move entirely before public timestamp.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/frontier_dsa_rating_migration/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: Country IMF/World Bank public DSA documents, sovereign events, IMF debt statistics, bond quotes and GDP vintages. Main model: Multi-state ordinal risk migration model with publication-aligned survival validation. Optional next step: Bayesian sovereign hazard with IMF policy intervention and restructuring recovery scenarios.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
