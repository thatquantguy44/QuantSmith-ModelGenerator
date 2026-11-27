---
name: opec-oil-balance-crack-spread
description: "OPEC Oil Balance Residuals and Refined Crack-Spread Transmission: reproducible, source-timed quantitative research design with independent falsification."
---
# SKILL — OPEC Oil Balance Residuals and Refined Crack-Spread Transmission
## When to use
When evaluating: Hedge product crack spreads when public crude production and stock-flow residuals imply inventory stress.

## Preconditions
Source entitlement, as-of clock and accounting convention for JODI monthly crude stocks/flows, OPEC reports, EIA refinery/product balances, crack-futures settlements; a defined decision and costed baseline.

## Procedure
1. Freeze H1: JODI stock-flow residuals after publication improve future refined crack-spread risk forecasts over oil price and seasonal inventories.; define H0 with cost-inclusive `Seasonal EIA weekly inventories and oil curve`.
2. Verify official pages and specific historical source versions. JODI typically publishes next-month and revises; align release date, not reporting month; execute only after release.
3. Build deterministic synthetic fixtures including: Monthly country submission corrections, unit conversion mismatches and sanctioned flow missingness..
4. Implement the baseline before trying `Constrained oil balance reconciliation and local-projection crack spread model`.
5. Test `Multi-region Bayesian trade flow accounting with measurement error and shipping lags` only if the simpler candidate survives.
6. Reconstruct economic costs and capacity: Use executable refined product futures, contract rolls, inventory and liquidity spreads; no inference from paper spreads..
7. Report Out-of-sample crack variance forecast, economic hedge cost, stock-balance residual stability plus negative-control confidence bounds.
8. Stop if: Residual predictive content disappears after vintages, shipping lags and front-month liquidity adjustment..
9. Prepare code hash, evidence ledger, and independent human review. No trading.

## Outputs
Proposed `manifest.json`, `source_ledger.json`, `baseline.json`, `candidate.json`, `robustness.md`, `decision.md`.
**These output files do not exist in this specification-only batch.**
## Reusability
Reuse point-in-time source gates, mathematical feasibility, cost contracts and paired economic evaluation; keep opec-oil-balance-crack-spread domain-specific features isolated.
