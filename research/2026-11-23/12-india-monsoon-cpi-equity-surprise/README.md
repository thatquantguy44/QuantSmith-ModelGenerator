# India Monsoon Surprise to Food CPI and Local Equity Pricing
**ID:** B17-12 · **Group:** Global/domestic quant research · **Geography:** India, state agriculture, INR and Indian listed consumer equities · **Priority:** 94/100 · **Status:** not implemented

## Economic decision and hypothesis
Calendar-average monsoon anomalies conceal crop-area heterogeneity and staggered CPI market dissemination.

**Decision:** Time/hedge exposures to monsoon-sensitive consumption and agriculture pricing after publicly available rainfall surprises.

**H1:** Rainfall surprises weighted by district crop patterns predict food-CPI subcomponents and cross-sectional consumer equity earnings revisions beyond national rainfall.

## Formulation
```text
Shock_t=Σ_d CropWeight_d*(Rain_d,t - Normal_d,t); ΔCPI_{t+h}=α+β*Shock_t+γ'Controls_t+ε
```
**Variables:** d district; crop weights fixed pre-season; h forecast horizon; normals from training vintage.

**Data:** IMD daily district rain, crop sowing weights, RBI CPI release, state-level harvest, NSE sector returns

**Clock:** IMD publication timestamp and next-tradable-session; CPI only after official release, no revisions used retroactively.

**Baseline:** All-India seasonal rainfall deviation plus autoregressive food CPI; **candidate:** Hierarchical spatial distributed-lag regression + causal crop weighting; **advanced:** Weather-to-crop graph structural state-space model with uncertainty propagation.

**Evaluation:** CPI MAE, sector neutral-return IC, hit rate net costs, seasonal robustness. **Failure:** No incremental holdout inflation forecast or stock-return effect against rainfall benchmark.

**Capacity:** Large liquid Indian stocks capacity feasible only with correct foreign-investor access, FX costs and exchange calendars.

**Illustrative sensitivity:** $160k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$100k/$240k. Resulting 24m net ROI **-100.0% / -11.5% / 112.5% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
