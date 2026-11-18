# 17. South African Power Reliability Equity Exposure

**QMG-20261116-17 · B — Domestic/global quant markets · Priority 85/100 (editorial judgment)**

**Geography/instruments:** South Africa; JSE industrials, retailers and exporters. **Difficulty:** High. **Production feasibility:** Public operational/filing pilot possible; spatial exposure and equity panel are unresolved. **Effort assumption:** One EM equity researcher and data engineer for 12-16 weeks.

## Problem, decision and economic value

National electricity availability affects firms unevenly because diesel backup, operating hours and plant location differ; a national outage headline is a poor cash-flow hedge. **Decision:** Build a sector/beta-neutral equity hedge against power-supply deterioration using pre-disclosed operational exposure. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** Exposure-weighted unplanned generation losses explain cash-flow/return sensitivity beyond national load-shedding stage, improving an outage hedge's downside loss by at least 10%.

## Mathematics and decision constraints

```text
R_it=alpha_i+date_t+beta*(exposure_i,pre*outage_t)+Gamma*controls_it+epsilon_it; min_w Var(R_portfolio-w'R_hedge)+k*turnover; beta_market'w=0, sector'w=0, |w_i|<=0.03
```

exposure_pre is firm energy intensity and backup dependence measured from disclosures before the study window; outage released unplanned unavailable capacity; R returns; controls include lagged commodity and FX factors; w hedge weights. beta is associational unless an independently defensible exogeneity design survives.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Eskom public system/outage releases, exact publication versions, issuer public energy/backup disclosures, geography, sector, JSE returns including delistings, ZAR and commodity controls. Historical spatial outage maps are an unresolved source gate. **Grain:** firm x day and dated generation/outage release. **Decision clock:** Update after verified Eskom publication; act next JSE session with prior-disclosed firm exposures. Never label realized electricity usage as known before earnings disclosure.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** National load-shedding stage interacted with fixed sector averages and a market/FX hedge.
- **Suggested candidate:** Panel fixed effects with pre-period exposure interactions and event-placebo tests.
- **Advanced alternative:** Hierarchical causal sensitivity bounds plus constrained cash-flow hedge portfolio.
- **Target:** power-shock residual equity sensitivity and hedge downside error.
- **Metrics:** hedge downside loss, residual exposure, out-of-sample fit, pretrend/placebo checks and net turnover cost.
- **Pre-registered stop/go:** GO if downside hedge error improves >=10%, coefficient sign is stable in held-out periods and net benefit survives doubled spreads; STOP causal interpretation if pretrends or commodity/FX confounds remain.
- **Critical negative test:** Use a future outage series as a placebo and randomize exposure labels within sectors; the real-time pipeline must reject future features and significance should vanish under label randomization.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $20m hedge sleeve capped at 1% ADV with local spreads, market access and ZAR hedge costs; concentrated names can exhaust capacity rapidly. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $20,000,000; annual net benefit scenarios -10/30/90 bps. Value channel: annual net hedge-loss reduction in cash-equivalent scenario terms, after trading and FX costs. Assume 9 months before benefit starts, 1.25 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$150,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $-20,000 | $-25,000 | -116.7% |
| Base | $60,000 | $75,000 | -50.0% |
| Upside | $180,000 | $225,000 | 50.0% |

Break-even annual benefit after launch = $120,000. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** High if exposure and timing can be made public and causal limits are respected; a careful negative result is valuable. **Key risk:** Power failures can reflect economic demand and maintenance choices; common national shocks do not supply clean quasi-random variation. Firms adopting solar are selected, and disclosure histories are incomplete.

**Cumulative novelty check:** Nearest: 2026-11-13/14 AI power capex and /17 US weather-energy hedging. New target is South African firm cash-flow exposure to generation reliability, with cross-sectional physical exposure and JSE equity hedges. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [Eskom data portal](https://www.eskom.co.za/dataportal/) — System performance portal and data-request process; historic first-public outage bulletins and spatial mappings are unverified. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed JSE total-return/delisting history, firm reference mapping and intraday prices if needed. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Optional public-company-approved operating exposure detail; never required or obtained for this public proposal. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Callaway and Sant'Anna, Difference-in-Differences with Multiple Time Periods](https://arxiv.org/abs/1803.09015) — Verified paper title/authors and identification assumptions; does not validate proposed market applications. Retrieval run: 2026-11-17T02:38:22+00:00.
- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
