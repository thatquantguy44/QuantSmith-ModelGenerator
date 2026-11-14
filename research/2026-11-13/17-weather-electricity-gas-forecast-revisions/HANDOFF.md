# HANDOFF — Weather Forecast Revision as an Electricity-to-Gas Risk Hedge
## Truthful current state
- **Research ID:** QMG-20261113-17 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** US regional power markets and Henry Hub-linked energy.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for NWS issued and archived forecasts, EIA balancing authority hourly load and generation, power/gas futures settlements and basis..
3. Prepare synthetic point-in-time fixture using grain balancing authority × weather forecast issuance × lead hour.
4. Implement the **Seasonal degree-day demand regression and absolute temperature forecasts.** cost-inclusive benchmark *before* Net-load forecast-revision elasticity with non-linear stress threshold..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: NWS API provides forecasts; EIA provides actual hourly grid operation data; forecast version history must be separately collected going forward.
- Licensed/permissioned input gap: Historical forecast-vintage archives and regional power/gas forward executable quotes.
- Material science risk: Archive of *historical forecasts as issued* may be inaccessible; today's historical observations are not contemporaneous forecasts.
- 24-month economics `-100% to 176%` reflect hypothetical sensitivity: hypothetical $10m energy risk sleeve with 0–235 bps annualized risk/carry improvements; outcomes uncertain.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Different from AI capex power bottlenecks: targets short-horizon physical weather forecast errors and energy hedging.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
