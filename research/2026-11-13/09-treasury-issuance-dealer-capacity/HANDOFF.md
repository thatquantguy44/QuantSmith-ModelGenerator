# HANDOFF — Treasury Issuance-to-Dealer Intermediation Capacity Map
## Truthful current state
- **Research ID:** QMG-20261113-09 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** United States issuance and dealer system.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for Treasury auction issuance and settlement schedule; weekly primary dealer net positions/financing; OFR repo aggregates; public Treasury yield changes..
3. Prepare synthetic point-in-time fixture using grain issuance cohort × week of publicly released dealer aggregates.
4. Implement the **Treasury yield volatility and calendar week indicators.** cost-inclusive benchmark *before* Event-study + state-space dealer supply absorption proxy..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: Treasury and NY Fed release events and dealer statistics publicly, though publication lags must be retained.
- Licensed/permissioned input gap: CUSIP prices and Treasury bond quote/liquidity microstructure.
- Material science risk: Aggregate dealer reports cannot identify securities or dealers and issuance is endogenous to financing conditions.
- 24-month economics `-75% to 70%` reflect hypothetical sensitivity: scenario: one avoided bad inventory allocation month or improved hedging stress alerts; not a measured signal.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Unlike earlier quarter-end seasonality or CUSIP specials relative value, models dealer system-wide absorption of issuance using lag-safe public aggregates.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
