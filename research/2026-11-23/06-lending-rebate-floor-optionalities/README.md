# Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes
**ID:** B17-06 · **Group:** Securities finance · **Geography:** EUR, CHF, JPY and USD cash-collateralized securities lending · **Priority:** 90/100 · **Status:** not implemented

## Economic decision and hypothesis
Minimum rebate or fee floors make effective funding convex at negative short rates; a linear spread assumption can misstate value.

**Decision:** Price and hedge rebate-floor optionality embedded in cash-collateral loan agreements.

**H1:** Contract-aware nonlinear floor valuation reduces forecast carry error and improper pricing vs linear spread assumptions.

## Formulation
```text
PV_floor=E^Q[Σ_t DF_t*CashCollateral_t*max(K-r_t,0)*Δt]; Revenue=baseFee+PV_floor-hedgeCost
```
**Variables:** K is contractual rebate floor, r_t relevant overnight collateral rate, DF discount factor, Δt year fraction.

**Data:** Historical overnight benchmarks, collateral currency curves, cash balances, contract rebate-floor clauses

**Clock:** Valuation at contract initiation using curve observed by quote cut-off, not future realized policy rates.

**Baseline:** Static contractual rebate minus benchmark with no optionality; **candidate:** Rate-tree floor valuation and curve calibration with contract clause parser; **advanced:** Multi-currency short-rate stochastic volatility and correlated collateral run-off scenario valuation.

**Evaluation:** Pricing replication error, stress carry, calibration error and limit-breach count. **Failure:** Valuation adds no meaningful incremental pricing accuracy to conservative quoted-fee schedules.

**Capacity:** Profit only if floors contractually negotiated; hedge notional and floor illiquidity restrict scale.

**Illustrative sensitivity:** $135k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$80k/$225k. Resulting 24m net ROI **-100.0% / -16.0% / 136.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
