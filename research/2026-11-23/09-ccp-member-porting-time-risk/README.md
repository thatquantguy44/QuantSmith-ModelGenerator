# CCP Member Default Position-Porting Time and Liquidity Optimization
**ID:** B17-09 · **Group:** Securities finance · **Geography:** Global cleared rates and repo portfolios · **Priority:** 87/100 · **Status:** not implemented

## Economic decision and hypothesis
Porting eligible positions can fail due to margin deadlines, client permissions and receiving-member constraints even with adequate default-fund assets.

**Decision:** Choose contingent porting routes and liquidity reserves for a hypothetical clearing-member default.

**H1:** A capacity-constrained porting algorithm lowers simulated liquidation shortfall and time-to-restore relative to static member choice.

## Formulation
```text
min_{x_{ij}} Σ_{ij} x_{ij}*(PortDelay_{ij}+λ*MarginShortfall_{ij}) subject to Σ_j x_{ij}≤Position_i, K_j≥Σ_i x_{ij}
```
**Variables:** x_ij assigned position notional, K_j receiving-member capacity; only eligible clients/contracts included.

**Data:** Public CCP rulebooks; synthetic position/eligibility and margin profiles; simulated member outage

**Clock:** Use rule versions effective on default scenario date, exclude assumptions from later CCP notices.

**Baseline:** Manual first-available eligible clearing member routing; **candidate:** Multi-period mixed-integer stochastic porting/survival flow simulator; **advanced:** Distributionally robust queueing network with correlated member liquidity and stress haircuts.

**Evaluation:** Porting completion by deadline, unmet margin, loss given port failure, rerouting overhead. **Failure:** No improvement in adverse default scenarios over conservative porting alternatives or reliance on forbidden client position data.

**Capacity:** Not a deployable CCP recovery plan; scenario policy must be vetted by legal and risk.

**Illustrative sensitivity:** $210k assumed total 24m development/data/maintenance cost; assumed launch in month 10; assumed annual gross outcome downside/base/upside $0k/$95k/$330k. Resulting 24m net ROI **-100.0% / -47.2% / 83.3% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
