# HANDOFF — CFTC Positioning Concentration and Commodity Curve Convexity
## Truthful current state
- **Research ID:** QMG-20261113-15 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** United States commodity futures with global supply chains.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for CFTC Disaggregated COT futures positions, futures contracts prices/rolls, EIA physical inventories where applicable..
3. Prepare synthetic point-in-time fixture using grain CFTC contract market × Tuesday reference position × Friday public release, then weekly trade clock.
4. Implement the **Futures curve carry/roll-yield and 12-month time-series momentum.** cost-inclusive benchmark *before* Positioning-conditioned conditional expected shortfall regression..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: CFTC public positioning has Tuesday reference dates and Friday releases; curve prices may be delayed/paid.
- Licensed/permissioned input gap: Executable futures historical bid/ask term structure and expiry calendars.
- Material science risk: CFTC taxonomy changes, combined report double-counting and slow publication may annihilate predictive edge.
- 24-month economics `-100% to 138%` reflect hypothetical sensitivity: hypothetical $20m risk budget, small tail-loss reduction in commodity futures over 24 months; benefits uncertain.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
No overlap with repo or market data research: tests commodity term-structure convexity interaction with lagged positioning.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
