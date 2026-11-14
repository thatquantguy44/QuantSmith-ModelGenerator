# HANDOFF — Settlement-Fail Buy-In versus Wait Optimal Stopping
## Truthful current state
- **Research ID:** QMG-20261113-06 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** US Treasury and agency settlement.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for Public dealer failure aggregates for calibration; synthetic failure life histories; approved buy-in quotes, fails charges and legal remedies..
3. Prepare synthetic point-in-time fixture using grain failed settlement instruction × elapsed failed day × cut-off timestamp.
4. Implement the **Auto-escalate after fixed N-day failure age.** cost-inclusive benchmark *before* Discrete-time survival model with exact dynamic-programming stopping rule..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: Primary dealer fails are aggregate benchmarks, not individual securities or cost histories.
- Licensed/permissioned input gap: Licensed dealer fail/cover reference prices and settlement clock information.
- Material science risk: Fails charges and rights to enforce buy-ins differ by asset, market and contract; wrong assumptions invalidate decisions.
- 24-month economics `-50% to 100%` reflect hypothetical sensitivity: scenario: fewer unnecessary emergency cover trades on an illustrative $150m failed notional portfolio over two years.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Earlier fail propagation research targeted network cascades; this is trade-specific optional stopping and remedy economics.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
