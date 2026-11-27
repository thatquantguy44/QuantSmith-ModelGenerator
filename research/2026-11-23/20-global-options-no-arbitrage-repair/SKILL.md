---
name: global-options-no-arbitrage-repair
description: "Arbitrage-Free Equity Volatility Surface Repair Across Markets: reproducible, source-timed quantitative research design with independent falsification."
---
# SKILL — Arbitrage-Free Equity Volatility Surface Repair Across Markets
## When to use
When evaluating: Produce arbitrage-consistent option risk surfaces and screen put-call/calendar violations before risk budgeting.

## Preconditions
Source entitlement, as-of clock and accounting convention for Time-synchronized option bid/ask, underlying forwards, dividends, exchange calendars, corporate action adjustments; a defined decision and costed baseline.

## Procedure
1. Freeze H1: Constrained surface repair reduces downstream hedge Greeks error and false arbitrage alarms versus independent spline fitting.; define H0 with cost-inclusive `Per-expiry unconstrained cubic interpolation with clip to bid/ask`.
2. Verify official pages and specific historical source versions. Quote timestamp aligned to each exchange session; repair uses no quotes from future or closed-market snapshots.
3. Build deterministic synthetic fixtures including: American vs European option styles, dividend marks, early exercise, restricted historical quote rights..
4. Implement the baseline before trying `Static no-arbitrage SVI/SSVI constrained calibration with conservative quote filters`.
5. Test `Joint multi-market neural stochastic volatility calibrated to arbitrage constraints and holidays` only if the simpler candidate survives.
6. Reconstruct economic costs and capacity: Surface repairs support quality/risk decisions first; apparent arbitrage cannot be traded without depth and cost..
7. Report Static arbitrage violations, held-out option price MAE, hedge delta error, false anomaly alerts plus negative-control confidence bounds.
8. Stop if: Constrained repair does not reduce out-of-sample pricing/hedging error or introduces hidden quote crossings..
9. Prepare code hash, evidence ledger, and independent human review. No trading.

## Outputs
Proposed `manifest.json`, `source_ledger.json`, `baseline.json`, `candidate.json`, `robustness.md`, `decision.md`.
**These output files do not exist in this specification-only batch.**
## Reusability
Reuse point-in-time source gates, mathematical feasibility, cost contracts and paired economic evaluation; keep global-options-no-arbitrage-repair domain-specific features isolated.
