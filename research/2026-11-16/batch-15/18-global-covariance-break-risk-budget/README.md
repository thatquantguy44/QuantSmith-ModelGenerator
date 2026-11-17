# 18. Global Covariance-Break Risk-Budget Controller

**QMG-20261116-18 · B — Domestic/global quant markets · Priority 94/100 (editorial judgment)**

**Geography/instruments:** US, Europe, Japan and liquid EM; equity, rates, FX and commodities. **Difficulty:** Medium. **Production feasibility:** High synthetic and delayed-public-proxy prototype; investable returns require licensed point-in-time instruments. **Effort assumption:** One portfolio researcher plus data engineer for 8-10 weeks.

## Problem, decision and economic value

A portfolio risk model can become most confident just before cross-asset correlations break, causing unstable risk budgets and costly rebalancing. **Decision:** Choose between holding current risk weights and a constrained rebalance when covariance-change evidence exceeds its execution cost. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** Sequential break detection with a no-trade region lowers realized risk-budget tracking error by at least 15% versus monthly EWMA rebalancing without increasing turnover.

## Mathematics and decision constraints

```text
min_(w,v) sum_i W_i*(RC_i(w,Sigma_hat)-v*b_i)^2+lambda*||w-w_prev||_1; RC_i=w_i*(Sigma_hat*w)_i/sqrt(w'Sigma_hat*w), v=sqrt(w'Sigma_hat*w), sum_i w_i=1, 0<=w_i<=cap_i, gross_risk_equivalent_leverage<=L
```

w long-only capital weights in predeclared liquid instruments; b target fractions of portfolio volatility summing to one; v total portfolio volatility; W positive error weights; Sigma_hat covariance estimated only from prior synchronized returns; lambda execution penalty; L gross risk-equivalent leverage if futures used. Change alarm selects a covariance window using past data only. This nonlinear risk-budget objective is not asserted convex; solver local/global status must be reported.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Daily index/futures/ETF total returns and FX, point-in-time instrument starts/ends, roll calendars, trading sessions, bid/ask and cost curves. H.15 can support rate diagnostics but is not a global total-return panel. **Grain:** instrument x completed local session x common information cutoff. **Decision clock:** Decide at 16:30 America/New_York using only completed market sessions and public data received by then; execute each market's next liquid session. Stale Asian observations remain lagged rather than filled with later prices.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Monthly risk parity using 60-day EWMA covariance and fixed weight caps; compare a simple shrinkage covariance with no break detection.
- **Suggested candidate:** Sequential covariance change detector plus shrinkage and cost-aware no-trade bands.
- **Advanced alternative:** Distributionally robust risk-budget optimization over post-break covariance ambiguity sets.
- **Target:** realized risk-contribution tracking error at matched turnover and volatility.
- **Metrics:** risk-budget RMSE, realized volatility overshoot, net return, drawdown, turnover and alarm false positives.
- **Pre-registered stop/go:** GO if risk-budget RMSE falls >=15% and turnover does not rise over >=3 held-out regimes and multiple asynchronous-market assumptions; STOP if improvement is due to more leverage, reduced target risk or tuned crisis dates.
- **Critical negative test:** Delay Japanese returns one extra session and perturb calendar alignment: claimed benefit should remain directionally stable; future-price replacement must fail an availability assertion.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $100m liquid multi-asset allocation; cap <=1% ADV and add market-specific impact, rolls and FX conversion. Capacity derives from instrument liquidity, not covariance model size. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $100,000,000; annual net benefit scenarios -5/10/25 bps. Value channel: annual net rebalancing/risk-control utility expressed in cash-equivalent bps at fixed target risk; no implied excess-return forecast. Assume 6 months before benefit starts, 1.5 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$140,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $-50,000 | $-75,000 | -153.6% |
| Base | $100,000 | $150,000 | 7.1% |
| Upside | $250,000 | $375,000 | 167.9% |

Break-even annual benefit after launch = $93,333. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** Medium-high: sequential decision value of covariance breaks with asynchronous-market controls; stronger novelty than adding a complex covariance estimator alone. **Key risk:** Look-ahead session alignment, ETF backfill, futures rolls and survivorship change the correlation structure. Same-day cross-market fills may be economically impossible.

**Cumulative novelty check:** Nearest: 2026-11-13/19 dynamic FX hedge. Currency hedge ratios are fixed here; the action is covariance-driven cross-asset risk rebalance timing, including rates and commodities. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [Federal Reserve H.15](https://www.federalreserve.gov/releases/h15/) — Published rate series and release schedule; daily observations are not executable intraday bond quotes. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed global point-in-time index/futures/ETF total returns with delistings, rolls and executable cost history. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Optional authorized portfolio limits and execution costs; synthetic constraints suffice for initial software. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
