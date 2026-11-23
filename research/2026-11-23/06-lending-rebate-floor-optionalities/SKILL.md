---
name: lending-rebate-floor-optionalities
description: "Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes: reproducible, source-timed quantitative research design with independent falsification."
---
# SKILL — Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes
## When to use
When evaluating: Price and hedge rebate-floor optionality embedded in cash-collateral loan agreements.

## Preconditions
Source entitlement, as-of clock and accounting convention for Historical overnight benchmarks, collateral currency curves, cash balances, contract rebate-floor clauses; a defined decision and costed baseline.

## Procedure
1. Freeze H1: Contract-aware nonlinear floor valuation reduces forecast carry error and improper pricing vs linear spread assumptions.; define H0 with cost-inclusive `Static contractual rebate minus benchmark with no optionality`.
2. Verify official pages and specific historical source versions. Valuation at contract initiation using curve observed by quote cut-off, not future realized policy rates.
3. Build deterministic synthetic fixtures including: Floor rights and term structures vary by legal agreement; historic negative-rate regimes have sample limitations..
4. Implement the baseline before trying `Rate-tree floor valuation and curve calibration with contract clause parser`.
5. Test `Multi-currency short-rate stochastic volatility and correlated collateral run-off scenario valuation` only if the simpler candidate survives.
6. Reconstruct economic costs and capacity: Profit only if floors contractually negotiated; hedge notional and floor illiquidity restrict scale..
7. Report Pricing replication error, stress carry, calibration error and limit-breach count plus negative-control confidence bounds.
8. Stop if: Valuation adds no meaningful incremental pricing accuracy to conservative quoted-fee schedules..
9. Prepare code hash, evidence ledger, and independent human review. No trading.

## Outputs
Proposed `manifest.json`, `source_ledger.json`, `baseline.json`, `candidate.json`, `robustness.md`, `decision.md`.
**These output files do not exist in this specification-only batch.**
## Reusability
Reuse point-in-time source gates, mathematical feasibility, cost contracts and paired economic evaluation; keep lending-rebate-floor-optionalities domain-specific features isolated.
