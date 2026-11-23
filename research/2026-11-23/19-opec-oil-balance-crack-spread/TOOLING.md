# TOOLING — OPEC Oil Balance Residuals and Refined Crack-Spread Transmission
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
pandas, statsmodels, scipy.optimize, pymc. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `OPEC producers, global crude and Atlantic Basin refined products` market calendar.
- `qmg_core.economics.CostModel`: Use executable refined product futures, contract rolls, inventory and liquidity spreads; no inference from paper spreads.
- `qmg_core.baselines.PolicyComparator`: Seasonal EIA weekly inventories and oil curve
- `qmg_core.evals.FalsificationGate`: Residual predictive content disappears after vintages, shipping lags and front-month liquidity adjustment.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/opec_oil_balance_crack_spread/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: JODI monthly crude stocks/flows, OPEC reports, EIA refinery/product balances, crack-futures settlements. Main model: Constrained oil balance reconciliation and local-projection crack spread model. Optional next step: Multi-region Bayesian trade flow accounting with measurement error and shipping lags.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
