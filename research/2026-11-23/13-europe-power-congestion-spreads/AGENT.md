# AGENT — European Interconnector Congestion Power-Spread State Estimator
**Agent name:** `qmg-europe-power-congestion-spreads-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `Transmission-capacity-corrected congestion states improve next-day risk classification and hedge calibration versus load-only spread models.` for the economic decision: Select hedged cross-zone power spread exposures conditional on public transfer constraints.. Geography: France, Germany, Benelux, Nordic and Iberian bidding zones. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: ENTSO-E day-ahead prices, transfer capacities, interconnector outages, wind/load forecasts and contract liquidity.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `Congestion regime Brier score, spread MAE, feasible net hedge carry and stress CVaR`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: pypsa, xarray, statsmodels, cvxpy. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and Cross-zone transmission rights and operational capacities not freely tradable; timestamps and price revisions. trigger human escalation.
**Escalation:** Spread gains disappear after simultaneous public forecast access, congestion settlement and capacity rights..
Public repo may contain synthetic fixtures and verified official links only.
