# Chile–Peru Copper Royalty Shock to Sovereign and Mining Credit
**ID:** B17-15 · **Group:** Global/domestic quant research · **Geography:** Chile and Peru, mining and sovereign USD/local-currency credit · **Priority:** 91/100 · **Status:** not implemented

## Economic decision and hypothesis
Copper price explains broad earnings but fiscal royalty changes can shift tax take and mine investment with different lags.

**Decision:** Hedge commodity-linked fiscal and issuer credit risk around public mining tax and royalty changes.

**H1:** Legislated effective marginal royalty changes predict issuer-versus-sovereign credit spread dispersion beyond copper returns.

## Formulation
```text
ΔSpread_{i,t+h}=β*Exposure_i*ΔRoyaltyRate_t+θ*ΔCopperPrice_t+γ'X_i,t+ε
```
**Variables:** Exposure_i public geographic mine revenue, ΔRoyaltyRate legislated effective tax not mere bill proposal.

**Data:** USGS production, government royalty statutes, country budgets, company annual filings, credit spreads and currency

**Clock:** Policy event recognized at official publication/enactment time; annual USGS data only upon issuance.

**Baseline:** Copper price beta plus sovereign spread changes; **candidate:** Event study with cross-sectional mine exposure and staggered law timing; **advanced:** Partial equilibrium mine-option tax model under investment deferral and country sovereign budget feedback.

**Evaluation:** Event abnormal spread, FX-adjusted carry, political timing placebo, credit risk attribution. **Failure:** No holdout effect after commodity beta and country shock controls or cannot identify legal effective date.

**Capacity:** Bid/ask for mining credits and FX may swamp basis; avoid assuming continuous trading around policy announcements.

**Illustrative sensitivity:** $170k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$95k/$260k. Resulting 24m net ROI **-100.0% / -25.5% / 103.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
