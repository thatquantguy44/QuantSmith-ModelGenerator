# 12. Brazil Inflation Diffusion versus Breakeven Carry

**QMG-20261116-12 · B — Domestic/global quant markets · Priority 87/100 (editorial judgment)**

**Geography/instruments:** Brazil; local nominal and inflation-linked government bonds. **Difficulty:** High. **Production feasibility:** Public expectations research feasible; executable real/nominal curves require access and local expertise. **Effort assumption:** One rates researcher plus data engineer for 12-16 weeks; local conventions review required.

## Problem, decision and economic value

Headline inflation surprises can mask changes in breadth and persistence; inflation-linked bond performance also includes indexation lags, carry and real-duration exposure. **Decision:** Choose a DV01-neutral nominal-versus-inflation-linked bond overlay using released inflation breadth and survey dispersion. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** Inflation-breadth revisions and Focus dispersion improve next-quarter breakeven return forecasts by at least 10% squared-error reduction versus carry plus headline surprise, and add 20 annualized net bps at fixed risk.

## Mathematics and decision constraints

```text
y_t=R_linked,t:t+63-h_t*R_nominal,t:t+63-index_carry_t; y_t=alpha+beta*diffusion_t+gamma*dispersion_t+delta*carry_t+epsilon; DV01_linked-h_t*DV01_nominal=0, |gross_DV01|<=K
```

R are local-currency total returns; h matches nominal to real-bond DV01 with residual inflation sensitivity reported; diffusion share of component price increases known at release; dispersion survey disagreement; index_carry mechanically known accrued indexation; K risk budget. USD investor FX exposure is hedged and charged separately.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

BCB public inflation/Focus releases, component-level official IPCA data to be resolved before implementation, dated expectations distributions, bond cash flows/indexation conventions, executable nominal and real curves and BRL hedge quotes. **Grain:** inflation release x survey public version x matched bond pair. **Decision clock:** Trade no earlier than next Sao Paulo session after verified inflation and survey publication, with one-hour processing lag. Survey collection dates are never treated as public timestamps.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Carry/roll plus headline inflation surprise using a fixed ridge regression and identical risk budget.
- **Suggested candidate:** Sparse distributed-lag regression with local-projection diagnostics.
- **Advanced alternative:** Bayesian inflation component state-space model with scenario-robust breakeven sizing.
- **Target:** 63-session DV01-neutral excess breakeven return net of mechanical carry.
- **Metrics:** out-of-sample MSE, net bps, real/nominal hedge residual, turnover, drawdown and calibration across inflation regimes.
- **Pre-registered stop/go:** GO if >=10% forecast MSE improvement and >=20 net annualized bps at unchanged risk with >=40 nonoverlapping quarterly outcomes; STOP if official component vintage or executable curve history cannot be established.
- **Critical negative test:** Set nominal and linked yields to parallel shifts with no inflation shock: residual P&L must reflect declared duration mismatch, not be mislabeled inflation alpha.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $40m duration-matched overlay; constrain pair DV01 and <=1% of observed issue turnover. Local liquidity, BRL hedging, indexation and applicable taxes must be priced before investment use. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $40,000,000; annual net benefit scenarios -10/20/60 bps. Value channel: annual incremental return after local bond bid/ask, carry, hedge, market-access and applicable tax assumptions. Assume 9 months before benefit starts, 1.25 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$180,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $-40,000 | $-50,000 | -127.8% |
| Base | $80,000 | $100,000 | -44.4% |
| Upside | $240,000 | $300,000 | 66.7% |

Break-even annual benefit after launch = $144,000. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** High if public component vintages can be assembled; tests information diffusion separately from mechanical indexation. **Key risk:** Overlapping quarterly labels create false sample size; inflation indexation/tax rules and market-access costs can erase apparent returns. No current Brazilian tax recommendation is assumed.

**Cumulative novelty check:** Nearest: 2026-11-13/13 US-euro curve shocks. This concerns local inflation breadth, indexation carry and Brazil nominal/real relative duration, with a distinct target and instrument set. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [BCB Focus market expectations](https://www.bcb.gov.br/en/monetarypolicy/marketexpectations) — Official survey description and public releases. A survey collection date is not necessarily the public release date. Retrieval run: 2026-11-17T02:38:22+00:00.
- [BCB expectations open-data catalog](https://opendata.bcb.gov.br/en/dataset/market-expectations) — Catalog and service references; no historical vintage panel or executable local bond prices downloaded. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed Brazilian nominal/real bond curves and constituent return/terms history; public BCB series are not executable curves. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Optional authorized execution data; no domestic account or trading permission established. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
