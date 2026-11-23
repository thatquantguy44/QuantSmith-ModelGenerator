# Arbitrage-Free Equity Volatility Surface Repair Across Markets
**ID:** B17-20 · **Group:** Global/domestic quant research · **Geography:** US, UK and Japan equity index listed options · **Priority:** 86/100 · **Status:** not implemented

## Economic decision and hypothesis
Sparse option quotes violate calendar and butterfly constraints due to stale prices, holidays and different exercise conventions.

**Decision:** Produce arbitrage-consistent option risk surfaces and screen put-call/calendar violations before risk budgeting.

**H1:** Constrained surface repair reduces downstream hedge Greeks error and false arbitrage alarms versus independent spline fitting.

## Formulation
```text
min_{σ_surface} Σ_{k,T} w_{k,T}(σ_{k,T}-σ_mid)^2 + λ*Smooth(σ) s.t. ∂_T TotalVar≥0, ConvexCall(K,T)≥0
```
**Variables:** k log-forward moneyness,T maturity; σ implied vol, w quote reliability; bounds depend on option exercise type.

**Data:** Time-synchronized option bid/ask, underlying forwards, dividends, exchange calendars, corporate action adjustments

**Clock:** Quote timestamp aligned to each exchange session; repair uses no quotes from future or closed-market snapshots.

**Baseline:** Per-expiry unconstrained cubic interpolation with clip to bid/ask; **candidate:** Static no-arbitrage SVI/SSVI constrained calibration with conservative quote filters; **advanced:** Joint multi-market neural stochastic volatility calibrated to arbitrage constraints and holidays.

**Evaluation:** Static arbitrage violations, held-out option price MAE, hedge delta error, false anomaly alerts. **Failure:** Constrained repair does not reduce out-of-sample pricing/hedging error or introduces hidden quote crossings.

**Capacity:** Surface repairs support quality/risk decisions first; apparent arbitrage cannot be traded without depth and cost.

**Illustrative sensitivity:** $185k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$105k/$265k. Resulting 24m net ROI **-100.0% / -24.3% / 91.0% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
