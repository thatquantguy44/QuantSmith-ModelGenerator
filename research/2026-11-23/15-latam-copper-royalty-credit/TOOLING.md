# TOOLING — Chile–Peru Copper Royalty Shock to Sovereign and Mining Credit
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
statsmodels, linearmodels, pandas, scipy. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `Chile and Peru, mining and sovereign USD/local-currency credit` market calendar.
- `qmg_core.economics.CostModel`: Bid/ask for mining credits and FX may swamp basis; avoid assuming continuous trading around policy announcements.
- `qmg_core.baselines.PolicyComparator`: Copper price beta plus sovereign spread changes
- `qmg_core.evals.FalsificationGate`: No holdout effect after commodity beta and country shock controls or cannot identify legal effective date.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/latam_copper_royalty_credit/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: USGS production, government royalty statutes, country budgets, company annual filings, credit spreads and currency. Main model: Event study with cross-sectional mine exposure and staggered law timing. Optional next step: Partial equilibrium mine-option tax model under investment deferral and country sovereign budget feedback.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
