# TOOLING — European Interconnector Congestion Power-Spread State Estimator
**Status:** proposed modules and dependencies; none installed in this PR.

## Domain-specific potential packages
pypsa, xarray, statsmodels, cvxpy. Pin exact compatible versions, lock hashes and document solver tolerances at implementation time; verify package licence and suitable model assumptions.

## Reusable cross-batch library contracts
- `qmg_core.sources.SnapshotSource.load(as_of, licence_class)`: original release and revision lineage.
- `qmg_core.time.AvailabilityIndex.filter(decision_time)`: no-later-than time filter.
- `qmg_core.contracts.EconomicState`: units, eligibility, `France, Germany, Benelux, Nordic and Iberian bidding zones` market calendar.
- `qmg_core.economics.CostModel`: Transmission rights/market access and collateral requirements dominate quoted spread opportunities.
- `qmg_core.baselines.PolicyComparator`: Historical seasonal hourly spread by zone pair
- `qmg_core.evals.FalsificationGate`: Spread gains disappear after simultaneous public forecast access, congestion settlement and capacity rights.
- `qmg_core.evidence.ClaimLedger`: verifiable external claims versus hypotheses.

## Project-specific package proposal
`src/qmg/research/europe_power_congestion_spreads/`: `contracts.py`, `source_adapter.py`, `baseline.py`, `candidate.py`, `objective.py`, `evals.py`, `cli.py`, `tests/test_publication_clock.py`, `tests/test_negative_controls.py`.
Domain input: ENTSO-E day-ahead prices, transfer capacities, interconnector outages, wind/load forecasts and contract liquidity. Main model: Physical-congestion regime HMM with capacity-constrained exposure mapper. Optional next step: Stochastic DC power flow and multi-region graph forecasts with out-of-area transfer shadow prices.

## Interface safety
Keep public/paid/private adapters separate; no token strings, client data or scrape-prohibited market data in the repository. Export proposed schema examples with **synthetic rows only**. Runtime and tests are not implemented.
