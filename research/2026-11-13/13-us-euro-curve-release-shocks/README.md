# US–Euro Sovereign Curve Shock Decomposition with Data Vintages
**B · Domestic & global markets** · **Priority 93/100** · **Difficulty Medium-high** · **Feasibility: High with public curve proxies** · **Publication interest 4/5 (conceptual, not a paper).**

## Why this exists
US and euro curve co-movement can come from common real-rate news, term-premium repricing or currency-hedged spillovers; identical correlations mask distinct hedge choices.

**Market / geography:** United States and euro area. **Asset classes:** rates, sovereign duration and curve risk.

## Falsifiable hypothesis and investment/operational decision
Vintaged macro-announcement decomposition reduces out-of-sample cross-market duration hedge error versus rolling beta.

**Decision:** Allocate DV01-neutral rates hedge exposure between US and European curve tenors after releases, subject to actual market liquidity..

## Research model
```text
Δy_US,t = β1*Surprise_US,t + β2*Surprise_EU,t + u_t; h*=argmin_h E[(ΔP_US+h*ΔP_EU)^2]+turnover_cost(h)
```
y is sovereign yield; Surprise is actual release minus consensus known beforehand (consensus may require licensing); h is DV01-scaled hedge.

## Data and decision clock
ECB published euro yield curve, US yields and ALFRED macro vintages, official release times, FX hedges, rates futures cost. **Observation grain:** economic release event × curve tenor × publication instant × geography. **Decision horizon:** end-of-release or next-session decision after releases disseminate; avoid falsely assuming instant access to revised series.

## Baseline versus candidate
- **Baseline:** 60-day rolling DV01-neutral cross-market beta hedge.
- **Proposed model:** Vintaged announcement factor model plus shrinkage hedge weights.
- **Advanced option:** Hierarchical structural yield-curve state-space with distinct real-rate and term-premium factor loading.
- **Primary metrics:** OOS hedging variance reduction, implementation shortfall, tail DV01 loss, signal turnover.
- **Falsification:** Reject if hedge variance does not improve at least 5% net of turnover on independent event holdout.
- **Primary economic or methodological caveat:** Public releases cannot recreate market consensus surprises without a licensed historical consensus dataset or explicit no-consensus baseline.

## 24-month ROI sensitivity (unverified assumptions only)
USD $165k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$355k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 115%**. NOT forecast or historical measurement. Economic lever: hypothetical $25m DV01-managed hedge sleeve with 0–120 bps equivalent annualized cost/risk improvement; not a backtest.

## Execution, capacity and feasibility
Restrict first pass to liquid Treasury/Bund futures and realistic FX basis and futures trading costs.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
