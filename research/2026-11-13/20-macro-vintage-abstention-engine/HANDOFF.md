# HANDOFF — Macro-Vintage Integrity Engine with Prediction Abstention
## Truthful current state
- **Research ID:** QMG-20261113-20 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** United States, euro area and OECD countries.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for ALFRED historical revisions, ECB yield releases, OECD SDMX data vintage calendars, US/global market proxies..
3. Prepare synthetic point-in-time fixture using grain economic indicator × observation period × release date × vintage ID.
4. Implement the **Always-on macro momentum score built from latest-vintage series.** cost-inclusive benchmark *before* As-of macro feature store with release-confidence model and abstention..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: FRED real-time API explicitly supports known-as-of periods; series availability and revision dates require series-specific verification.
- Licensed/permissioned input gap: Timestamped institutional macro-surprise and market execution data if transformed into a strategy.
- Material science risk: ALFRED historical series coverage, future revisions and OECD methodological breaks can be incomplete; abstention selection bias.
- 24-month economics `-85% to 88%` reflect hypothetical sensitivity: scenario: reduce failed model deployment and wasted model-validation hours, plus any trading uplift; 24-month benefits unmeasured.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Unlike curve-event alpha, this is a reusable *data integrity and decision abstention* engine applicable across global macro research.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
