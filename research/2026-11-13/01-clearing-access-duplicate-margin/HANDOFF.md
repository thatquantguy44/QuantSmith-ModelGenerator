# HANDOFF — Treasury Clearing Access-Path & Duplicate-Margin Optimizer
## Truthful current state
- **Research ID:** QMG-20261113-01 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** United States; cleared cash Treasury and repo.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for Eligible trade templates; path availability; historical quote spreads; initial/variation margin stress; capital/CCLF allocation; modeled netting sets; direct/sponsored/agent fees..
3. Prepare synthetic point-in-time fixture using grain trade × eligible clearing access path × decision timestamp.
4. Implement the **Minimize executable repo rate ignoring path-specific costs, after validating that every route is eligible.** cost-inclusive benchmark *before* Mixed-integer convex routing with separate margin, settlement and liquidity shadow prices..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: SEC and DTCC rules describe access but do not provide participant-specific margin or allocation cost.
- Licensed/permissioned input gap: Licensable transaction/quote history, margin-model input services and settlement reference data.
- Material science risk: Clearing rule exemptions and netting eligibility vary; estimated margin offsets could be nonportable across entities.
- 24-month economics `-43% to 121%` reflect hypothetical sensitivity: assume 2–8 bps avoidable total cost on an eligible hypothetical $250m continuously financed at ~1yr equivalent and fraction of volume attainable; capture model must account for actual turnover.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Different from earlier repo term-dislocation work: selects access/clearing topology under route-specific margin and legal constraints rather than predicting term rates.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
