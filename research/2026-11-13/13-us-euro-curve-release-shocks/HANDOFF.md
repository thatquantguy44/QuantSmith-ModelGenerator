# HANDOFF — US–Euro Sovereign Curve Shock Decomposition with Data Vintages
## Truthful current state
- **Research ID:** QMG-20261113-13 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** United States and euro area.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for ECB published euro yield curve, US yields and ALFRED macro vintages, official release times, FX hedges, rates futures cost..
3. Prepare synthetic point-in-time fixture using grain economic release event × curve tenor × publication instant × geography.
4. Implement the **60-day rolling DV01-neutral cross-market beta hedge.** cost-inclusive benchmark *before* Vintaged announcement factor model plus shrinkage hedge weights..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: ECB and FRED provide curves/vintages but not executable futures bid/ask or consensus expectation snapshots.
- Licensed/permissioned input gap: Timestamped macro consensus, Treasury/Bund futures quotes and instrument rolls.
- Material science risk: Public releases cannot recreate market consensus surprises without a licensed historical consensus dataset or explicit no-consensus baseline.
- 24-month economics `-100% to 115%` reflect hypothetical sensitivity: hypothetical $25m DV01-managed hedge sleeve with 0–120 bps equivalent annualized cost/risk improvement; not a backtest.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Separate from repo term structure: this is cross-market interest-rate hedge decomposition around scheduled macro news.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
