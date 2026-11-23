# European Interconnector Congestion Power-Spread State Estimator
**ID:** B17-13 · **Group:** Global/domestic quant research · **Geography:** France, Germany, Benelux, Nordic and Iberian bidding zones · **Priority:** 93/100 · **Status:** not implemented

## Economic decision and hypothesis
Observed day-ahead power spread contains congestion rents, bidding-zone rules and renewable shocks; unconstrained price regressions overstate arbitrage.

**Decision:** Select hedged cross-zone power spread exposures conditional on public transfer constraints.

**H1:** Transmission-capacity-corrected congestion states improve next-day risk classification and hedge calibration versus load-only spread models.

## Formulation
```text
Spread_{a,b,t}=Price_a,t-Price_b,t; Flow_{ab,t}≤ATC_{ab,t}; max_q E[q*Spread-CongestionCost(q)] with |q|≤AccessCap
```
**Variables:** a,b bidding zones; ATC available transfer capacity; q a hypothetical permitted hedge, not a physically available arbitrage.

**Data:** ENTSO-E day-ahead prices, transfer capacities, interconnector outages, wind/load forecasts and contract liquidity

**Clock:** Only ENTSO-E forecasts published before day-ahead bidding deadline; actual flows/prices are evaluation targets.

**Baseline:** Historical seasonal hourly spread by zone pair; **candidate:** Physical-congestion regime HMM with capacity-constrained exposure mapper; **advanced:** Stochastic DC power flow and multi-region graph forecasts with out-of-area transfer shadow prices.

**Evaluation:** Congestion regime Brier score, spread MAE, feasible net hedge carry and stress CVaR. **Failure:** Spread gains disappear after simultaneous public forecast access, congestion settlement and capacity rights.

**Capacity:** Transmission rights/market access and collateral requirements dominate quoted spread opportunities.

**Illustrative sensitivity:** $220k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$150k/$355k. Resulting 24m net ROI **-100.0% / -14.8% / 101.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
