# Borrow Scarcity Causal Effect on Equity Market-Maker Quoted Depth
**ID:** B17-05 · **Group:** Securities finance · **Geography:** US equities and select developed markets · **Priority:** 91/100 · **Status:** not implemented

## Economic decision and hypothesis
Borrow fee spikes coincide with volatility and funding stress; ordinary cross-sectional regressions confuse cause and effect.

**Decision:** Adjust financing risk capital for equity liquidity provision when short-sale borrow becomes scarce.

**H1:** Exogenous changes to borrow supply lower subsequent displayed depth/increase effective spreads more than matched control stocks.

## Formulation
```text
Depth_{i,t}=α_i+δ_t+β*BorrowSupplyShock_{i,t}+γ'X_{i,t}+ε_{i,t}; H0: β=0
```
**Variables:** BorrowSupplyShock is preannounced/exogenous eligible inventory change; X contains liquidity and issuer controls.

**Data:** Borrow availability and fees, market quotes/trades, issuer event calendars and exclusion instruments

**Clock:** Quote-decision timing after actual supply notice; event timestamps distinguish pre-event leak, regular session and close.

**Baseline:** Spread/depth forecasting using only realized volatility and market cap; **candidate:** Matched differences-in-differences/event-time instrumental analysis; **advanced:** Structural market-maker inventory equilibrium with dynamic borrowing constraint.

**Evaluation:** Event-time β confidence interval, placebos, effective spread, depth and incremental risk price. **Failure:** No pre-registered effect with valid pretrends/instruments or effect only on illiquid untradeable names.

**Capacity:** Not an unconditional trading signal; capacity depends on quote depth and borrow clearance, include adverse selection.

**Illustrative sensitivity:** $220k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$120k/$310k. Resulting 24m net ROI **-100.0% / -31.8% / 76.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
