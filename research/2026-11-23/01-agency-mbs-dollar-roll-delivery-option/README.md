# Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option
**ID:** B17-01 · **Group:** Securities finance · **Geography:** United States / agency MBS TBA · **Priority:** 96/100 · **Status:** not implemented

## Economic decision and hypothesis
TBA rolls embed delivery-option value; treating the drop as a pure financing rate may underprice pool selection and settlement frictions.

**Decision:** Select TBA dollar-roll financing and permissible pool delivery sets versus holding specified pools financed through repo.

**H1:** Explicit deliverability and pool opportunity costs explain dollar-roll implied funding differences beyond coupon, term and simple financing spreads.

## Formulation
```text
min_{q_p>=0} Σ_p q_p*(PoolCarry_p + DeliveryCost_p - RollDrop_p), subject to Σ_p q_p = DeliverableNotional, 0<=q_p<=PoolAvailable_p*Eligible_p
```
**Variables:** x_p is assigned pool fraction/selection, RollDrop is dollar-roll price drop, Eligible_p delivery eligibility; preserve coupon/payup units.

**Data:** TBA front/back prices, pools, payups, coupon schedules, specified-pool risk, MBSD netting, EPN eligibility and execution costs

**Clock:** Decision at pre-roll executable quote; EPN pool assignment becomes known later and must not leak into earlier signals.

**Baseline:** Dollar-roll implied financing vs same-tenor generic repo without delivery-option valuation; **candidate:** Constrained pool-delivery optimizer with observable pool financing carry and roll prices; **advanced:** Stochastic pool quality and delivery-selection real-options game with cheapest-deliverable simulation.

**Evaluation:** Net financing bps, cheapest-deliverable premium, pre-settlement fail exposure, netted capital and tail regret. **Failure:** No stable out-of-sample cost-adjusted advantage over delivery-aware manual baseline at realistic pool eligibility.

**Capacity:** Market depth and eligible pool inventory limit size; include bid/ask, delivery allocations, financing and clearing margin.

**Illustrative sensitivity:** $180k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$130k/$260k. Resulting 24m net ROI **-100.0% / 8.3% / 116.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
