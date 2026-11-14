# HANDOFF — Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
## Truthful current state
- **Research ID:** QMG-20261113-16 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** United States investment-grade/high-yield credit; optional Europe comparison.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for FINRA TRACE public aggregate/trade pages, subscription historical bond records, ETF market prices, NAV timestamps, bond indices, CDX basis..
3. Prepare synthetic point-in-time fixture using grain bond × disseminated trade timestamp × ETF NAV publication timestamp.
4. Implement the **ETF realized volatility and quoted bid-ask spread.** cost-inclusive benchmark *before* Robust bond-liquidity dispersion index and ETF tracking-state model..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: FINRA explains TRACE reporting and offers public aggregates; institutional historical tick panels may require subscription.
- Licensed/permissioned input gap: Full historic TRACE and ETF NAV indicative basket/creation data; licensed CDX/credit curves.
- Material science risk: Reported bond prices may be size-capped/delayed; TRACE trade access/licensing varies and NAV can embed stale marks.
- 24-month economics `-100% to 112%` reflect hypothetical sensitivity: hypothetical $20m credit hedge program, saving a fraction of tracking-loss during rare liquidity events; no realized estimate.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Different from financing fail or collateral models: focuses public-market credit ETF tracking and bond secondary liquidity.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
