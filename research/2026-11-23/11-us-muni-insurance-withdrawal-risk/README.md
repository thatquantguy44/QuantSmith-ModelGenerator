# US Municipal Credit Vulnerability to Local Insurance Withdrawal
**ID:** B17-11 · **Group:** Global/domestic quant research · **Geography:** United States coastal, wildfire and flood-exposed municipal issuers · **Priority:** 95/100 · **Status:** not implemented

## Economic decision and hypothesis
Tax-base deterioration from insurance affordability may be a forward municipal credit risk not captured by standard debt ratios.

**Decision:** Prioritize municipal-credit surveillance and pricing by property tax base sensitivity to insurance availability.

**H1:** Hazard exposure × insurance withdrawal proxies predict later tax-roll stress/spread changes beyond debt-service coverage and demographics.

## Formulation
```text
ΔCreditSpread_{c,t+h}=β*(Hazard_c×InsuranceShock_{c,t})+γ'X_{c,t}+μ_c+τ_t+ε
```
**Variables:** c is issuer county/service area, h forward horizon; InsuranceShock uses published insurer exit/premium information.

**Data:** County FEMA risk, EMMA issuer disclosures, municipal price quotes, property valuations, insurer exit/public rate filings

**Clock:** County/issuer boundary vintage and disclosure posting timestamp; FEMA risk version frozen at decision date.

**Baseline:** Debt-to-revenue and issuer-rating-only spread screen; **candidate:** Geospatial panel DiD with insurance availability shock and issuer boundary crosswalk; **advanced:** Graph exposure propagation into municipal tax receipts with heterogeneous hazard risk.

**Evaluation:** Out-of-sample spread rank IC, change in tax revenue, false alerts, distress recall. **Failure:** No incremental out-of-time predictive effect after socioeconomic covariates and issuer-selection controls.

**Capacity:** Muni bonds illiquid, spread carry/horizon may exceed signal; favor risk-monitoring before trading.

**Illustrative sensitivity:** $160k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$100k/$260k. Resulting 24m net ROI **-100.0% / -11.5% / 130.2% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
