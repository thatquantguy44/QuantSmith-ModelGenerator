# TOOLING — US Bank Deposit Beta and Mark-to-Market Securities Run Risk
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
statsmodels, polars, pymc, duckdb. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `US regional banks and bank-sector equity/credit` market calendar.
- `qmg_core.economics.CostModel`: Large regional bank equity/cash bonds viable; small banks thin, CDS pricing inaccessible and not required for public proxy.
- `qmg_core.baselines.PolicyComparator`: Uninsured deposit share plus book capital ratio
- `qmg_core.evals.FalsificationGate`: No incremental forecast versus capital/deposit mix baseline after strict public release lag.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/us_bank_deposit_beta_run_risk/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: FDIC bank Call Reports, quarterly uninsured deposits, HTM/AFS loss fields, benchmark rates, bank equity CDS. Main model: Hierarchical deposit beta estimation plus accounting-based duration stress. Optional next step: Agent-based depositor migration with liquidity haircut and contagion sensitivity.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
