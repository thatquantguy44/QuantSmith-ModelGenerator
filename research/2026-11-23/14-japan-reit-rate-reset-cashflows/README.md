# Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization
**ID:** B17-14 · **Group:** Global/domestic quant research · **Geography:** Japan J-REITs and commercial real estate · **Priority:** 92/100 · **Status:** not implemented

## Economic decision and hypothesis
Nominal Japanese policy changes transmit unevenly to fixed versus floating J-REIT liabilities and rental pass-through.

**Decision:** Distinguish J-REIT rate-reset liability timing and property yield spreads rather than duration-only price sensitivity.

**H1:** Public debt-maturity reset exposure explains post-policy J-REIT return dispersion beyond NAV discount and generic duration beta.

## Formulation
```text
CashInterest_{i,t+h}=Σ_m Debt_{i,m}*(Coupon_{i,m}+ResetBeta_{i,m}*ΔRate_t); ΔAFFO_i≈-ΔCashInterest_i+RentPassThrough_i
```
**Variables:** i REIT, m debt tranche, ResetBeta contractual floating/reset sensitivity; AFFO cash flow.

**Data:** BOJ rate time series, J-REIT bond/debt disclosures, rent index, total returns and market-based NAV

**Clock:** Use release/filing acceptance before BOJ event and timestamp debt disclosure versions.

**Baseline:** Market REIT index duration and price-to-NAV score; **candidate:** Disclosure-derived maturity-wall factor with event-based hedged return regressions; **advanced:** Tenant lease rollover and financing reset structural cash-flow model.

**Evaluation:** AFFO forecast error, sector-neutral return IC, liquidity-adjusted drawdown, event placebo. **Failure:** No incremental post-rate-shift forecast after issuer fixed-effects and NAV-duration controls.

**Capacity:** J-REIT constituent liquidity, FX hedge and foreign-investor restrictions limit realized capacity.

**Illustrative sensitivity:** $150k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$85k/$235k. Resulting 24m net ROI **-100.0% / -19.7% / 121.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
