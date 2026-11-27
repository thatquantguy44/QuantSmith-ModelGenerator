---
name: europe-power-congestion-spreads
description: "European Interconnector Congestion Power-Spread State Estimator: reproducible, source-timed quantitative research design with independent falsification."
---
# SKILL — European Interconnector Congestion Power-Spread State Estimator
## When to use
When evaluating: Select hedged cross-zone power spread exposures conditional on public transfer constraints.

## Preconditions
Source entitlement, as-of clock and accounting convention for ENTSO-E day-ahead prices, transfer capacities, interconnector outages, wind/load forecasts and contract liquidity; a defined decision and costed baseline.

## Procedure
1. Freeze H1: Transmission-capacity-corrected congestion states improve next-day risk classification and hedge calibration versus load-only spread models.; define H0 with cost-inclusive `Historical seasonal hourly spread by zone pair`.
2. Verify official pages and specific historical source versions. Only ENTSO-E forecasts published before day-ahead bidding deadline; actual flows/prices are evaluation targets.
3. Build deterministic synthetic fixtures including: Cross-zone transmission rights and operational capacities not freely tradable; timestamps and price revisions..
4. Implement the baseline before trying `Physical-congestion regime HMM with capacity-constrained exposure mapper`.
5. Test `Stochastic DC power flow and multi-region graph forecasts with out-of-area transfer shadow prices` only if the simpler candidate survives.
6. Reconstruct economic costs and capacity: Transmission rights/market access and collateral requirements dominate quoted spread opportunities..
7. Report Congestion regime Brier score, spread MAE, feasible net hedge carry and stress CVaR plus negative-control confidence bounds.
8. Stop if: Spread gains disappear after simultaneous public forecast access, congestion settlement and capacity rights..
9. Prepare code hash, evidence ledger, and independent human review. No trading.

## Outputs
Proposed `manifest.json`, `source_ledger.json`, `baseline.json`, `candidate.json`, `robustness.md`, `decision.md`.
**These output files do not exist in this specification-only batch.**
## Reusability
Reuse point-in-time source gates, mathematical feasibility, cost contracts and paired economic evaluation; keep europe-power-congestion-spreads domain-specific features isolated.
