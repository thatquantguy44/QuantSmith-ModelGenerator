# OPEC Oil Balance Residuals and Refined Crack-Spread Transmission
**ID:** B17-19 · **Group:** Global/domestic quant research · **Geography:** OPEC producers, global crude and Atlantic Basin refined products · **Priority:** 87/100 · **Status:** not implemented

## Economic decision and hypothesis
Production announcements are not physical barrels; apparent balance discrepancies may reflect reporting lags and revision practices.

**Decision:** Hedge product crack spreads when public crude production and stock-flow residuals imply inventory stress.

**H1:** JODI stock-flow residuals after publication improve future refined crack-spread risk forecasts over oil price and seasonal inventories.

## Formulation
```text
Residual_{c,m}=Production+Imports-Exports-RefineryIntake-ΔStocks-OtherUse; Crack_t=P_product_t-ConversionRatio*P_crude_t
```
**Variables:** c country,m reporting month; residual is diagnostic with units normalized; price conversion reflects barrel yields.

**Data:** JODI monthly crude stocks/flows, OPEC reports, EIA refinery/product balances, crack-futures settlements

**Clock:** JODI typically publishes next-month and revises; align release date, not reporting month; execute only after release.

**Baseline:** Seasonal EIA weekly inventories and oil curve; **candidate:** Constrained oil balance reconciliation and local-projection crack spread model; **advanced:** Multi-region Bayesian trade flow accounting with measurement error and shipping lags.

**Evaluation:** Out-of-sample crack variance forecast, economic hedge cost, stock-balance residual stability. **Failure:** Residual predictive content disappears after vintages, shipping lags and front-month liquidity adjustment.

**Capacity:** Use executable refined product futures, contract rolls, inventory and liquidity spreads; no inference from paper spreads.

**Illustrative sensitivity:** $170k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$115k/$280k. Resulting 24m net ROI **-100.0% / -4.2% / 133.3% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
