# HANDOFF — Dynamic Currency-Hedge and Rebalancing Tax for Global Equity
## Truthful current state
- **Research ID:** QMG-20261113-19 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** US, Japan, euro area, UK and selected liquid EM equity markets.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for Country index total returns, currency spot/forward curves, FX liquidity, investability restrictions and funding rates..
3. Prepare synthetic point-in-time fixture using grain country equity market × FX forward tenor × monthly rebalance date.
4. Implement the **50% static currency hedges plus equal-risk country weights and quarterly turnover.** cost-inclusive benchmark *before* Robust covariance and transaction-cost-aware FX hedge optimizer..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: MSCI publishes methodology, not unrestricted total return/constituent history; FX and rates data may have licensing restrictions.
- Licensed/permissioned input gap: Licensed global total return index histories, executable FX forwards and capital-control calendars.
- Material science risk: Country index histories have vendor survivorship and free-float methodological changes; FX pricing may be unavailable at allocated size.
- 24-month economics `-85% to 100%` reflect hypothetical sensitivity: hypothetical $30m equity exposure; 0–42 bps annually saved from hedge inefficiency and drawdown control; weak scenario still pays some operational value.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Not the previously studied cross-currency repo routing: this is an asset-allocation hedge problem across global stock indices.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
