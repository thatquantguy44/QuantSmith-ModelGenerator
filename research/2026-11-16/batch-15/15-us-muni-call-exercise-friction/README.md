# 15. US Municipal Call-Exercise Friction Surface

**QMG-20261116-15 · B — Domestic/global quant markets · Priority 88/100 (editorial judgment)**

**Geography/instruments:** United States tax-exempt callable municipal bonds. **Difficulty:** High. **Production feasibility:** Public-document sample feasible; broad pricing and identifier rights are licensed dependencies. **Effort assumption:** One municipal researcher and one document/data engineer for 12-16 weeks.

## Problem, decision and economic value

A callable bond's yield-to-worst can ignore heterogeneous issuer refinancing friction, notice timing and call execution, distorting duration and reinvestment risk. **Decision:** Choose between matched callable bonds using a calibrated call hazard and cash-flow stress rather than yield-to-worst alone. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** Issuer-friction call probabilities reduce one-year cash-flow forecast error by at least 15% versus deterministic first-economic-call exercise and improve net matched-bond selection by 15 bps per annum.

## Mathematics and decision constraints

```text
P(call_it=1|alive)=logit^-1(alpha+beta*refi_saving_it-gamma*friction_i+delta*notice_state_it); P_i=sum_s P(s|I_t)*sum_tau CF_i,tau(s)*D_t(tau); duration_limit<=K, issuer_weight<=0.05
```

refi_saving is modeled present-value saving using only as-of curves and permitted call terms; friction includes issue size and previously disclosed covenants; notice_state records public call notice; CF scenario cash flows; D discount factors; K duration-risk cap. Tax treatment is a declared investor scenario, not personalized advice.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

EMMA official statements and public call notices, contemporaneously released issuer financials, trades with dissemination timestamps, call schedules, accrued interest and matched yield curves. Public browsing is not assumed licensed bulk extraction. **Grain:** bond x call opportunity x public notice/financial filing event. **Decision clock:** Use only disclosures disseminated by prior close; trade at next obtainable firm offer/bid with a one-session latency. A call notice must enter at publication, not retroactively at the optional call date.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Exercise at first call date when modeled refunding savings exceed a fixed 3% threshold; compare yield-to-worst selection.
- **Suggested candidate:** Discrete-time survival model with economic refunding covariates.
- **Advanced alternative:** Hierarchical issuer stopping model with financing frictions and cash-flow scenario valuation.
- **Target:** call timing distribution, cash-flow forecast error and duration-adjusted bond return.
- **Metrics:** Brier score, cash-flow MAE, duration error, net matched return, spread/size sensitivity and call calibration.
- **Pre-registered stop/go:** GO if >=15% cash-flow MAE reduction and >=15 net annualized bps on >=500 held-out call opportunities; STOP if trade-vs-quote bias or missing failed/uncalled bonds explains gains.
- **Critical negative test:** Insert a public call notice after the prior-close cutoff: the model must not predict certainty before disclosure. A noncallable bond must have zero optional call hazard.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $40m matched-bond sleeve; cap issue ownership and trade size relative to observed turnover, allow days to execute and charge dealer markup. No presumption of instantaneous municipal execution. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $40,000,000; annual net benefit scenarios -5/20/50 bps. Value channel: annual incremental net selection/cash-flow-management value after municipal execution costs under a declared tax scenario. Assume 9 months before benefit starts, 1.25 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$170,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $-20,000 | $-25,000 | -114.7% |
| Base | $80,000 | $100,000 | -41.2% |
| Upside | $200,000 | $250,000 | 47.1% |

Break-even annual benefit after launch = $136,000. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** High: exercise frictions and segmented fixed income; strong public-document reproducibility potential. **Key risk:** Issuer credit, tax law, refunding restrictions and tender/redemption mechanics vary. Trade marks are not executable offers; repeated bonds from one issuer inflate sample size.

**Cumulative novelty check:** No archived municipal call project; distinct from single-fail buy-in stopping because the economic option belongs to a bond issuer and changes investor cash flows. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [MSRB about EMMA](https://www.msrb.org/Transparency-and-Technology/About-EMMA) — Free access to disclosures and trade information; bulk subscriptions and identifier rights are separate. Retrieval run: 2026-11-17T02:38:22+00:00.
- [MSRB trade data](https://www.msrb.org/Trade-Data) — Reporting and dissemination description; reported trades are not firm executable offers. Retrieval run: 2026-11-17T02:38:22+00:00.
- [Federal Reserve H.15](https://www.federalreserve.gov/releases/h15/) — Published rate series and release schedule; daily observations are not executable intraday bond quotes. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

MSRB bulk subscription, bond terms/identifier rights and executable dealer quote history as required. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Optional authorized execution quotes and investor constraint profiles; absent. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
