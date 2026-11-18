# 20. Australian Water Allocation Shadow Price and Crop Basis

**QMG-20261116-20 · B — Domestic/global quant markets · Priority 81/100 (editorial judgment)**

**Geography/instruments:** Murray-Darling Basin, Australia; water allocations and agricultural exposure. **Difficulty:** High. **Production feasibility:** Public market-data pilot feasible; regional crop/transfer constraints and hedge basis remain unresolved. **Effort assumption:** One agricultural researcher, water-domain reviewer and engineer for 12-18 weeks.

## Problem, decision and economic value

A water allocation price can be a local scarcity shadow price rather than a national crop signal; treating reported trades as immediate public prices can create fictitious foresight. **Decision:** Choose regional agricultural exposure or a crop-futures hedge only when released water scarcity changes affect a documented crop budget and survive basis costs. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** Allocation-decision surprises and transfer-constrained water shadow prices improve regional crop-margin forecasts by at least 10% versus seasonal water availability, and reduce hedge downside error by 5% net of costs.

## Mathematics and decision constraints

```text
max_(a,w) sum_c crop_price_c*yield_c(w_c)*a_c-water_price*w_c-other_cost_c*a_c; sum_c w_c<=allocation, transfer_flow_z<=limit_z; hedge_h=min E[(margin-h*crop_futures)^2]+k*abs(h)
```

c crop; a planted area; w irrigation water ML; yield response fixed from prior agronomic evidence; allocation released entitlement volume; z transfer zone; h futures hedge units; crop_price and water_price are as-of observations with reporting lags. No physical water trading rights are assumed.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

BOM public allocation decisions and water trades, first-publication/registration timestamps, transfer-zone limits, crop budgets, planting calendars and regional prices; licensed crop futures/basis and official agronomic response data to be resolved. **Grain:** water zone x allocation release x reported trade and crop season. **Decision clock:** Update only after verified allocation announcement; water transaction price enters at public reporting time, not settlement/trade date. Trade a hedge no earlier than next liquid session; use seasons as independent split units.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Seasonal allocation-volume score with a fixed regional crop basket and constant futures hedge ratio.
- **Suggested candidate:** Constrained crop-water optimization with allocation-shock local projections.
- **Advanced alternative:** Stochastic water/crop dynamic program and robust partial hedge across transfer zones.
- **Target:** regional crop-margin forecast and hedge basis-adjusted downside loss.
- **Metrics:** crop-margin MAE, net hedge downside loss, basis risk, transfer-feasibility, water-price interval coverage and turnover.
- **Pre-registered stop/go:** GO if margin MAE improves >=10% and net hedge downside loss >=5% across >=8 independently held-out seasons/zones; STOP if publication lag eliminates signal or local scarcity has no stable tradable crop exposure.
- **Critical negative test:** Give identical aggregate water to two disconnected zones: optimization must retain different shadow prices; delaying trade reporting must move its first eligible feature date.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $15m agricultural exposure, small research capacity. Limit futures to <=1% lagged volume; water transactions require separate legal/access review and are not assumed executable by the researcher. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $15,000,000; annual net benefit scenarios -10/40/120 bps. Value channel: annual incremental crop-margin hedge benefit after basis, transfer and futures execution costs in USD-equivalent planning scenarios. Assume 9 months before benefit starts, 1.25 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$160,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $-15,000 | $-18,750 | -111.7% |
| Base | $60,000 | $75,000 | -53.1% |
| Upside | $180,000 | $225,000 | 40.6% |

Break-even annual benefit after launch = $128,000. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** High interdisciplinary potential, but weak tradable hedge linkage makes this an intentionally lower-priority contrarian project. **Key risk:** Water rights, allocation trades and permanent entitlements are different assets. Thin reported prices, changing transfer limits and endogenous crop choice can defeat identification; crop futures may be a poor regional hedge.

**Cumulative novelty check:** Nearest: 2026-11-13/15 commodity crowding and /17 weather-energy revisions. This values allocation rights and transfer constraints in Australian agricultural production; no positioning signal or weather-forecast trade is reused. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [Australian Bureau of Meteorology water market information](https://www.bom.gov.au/water/market/) — Allocation decisions and water trades; trade reporting delay and regional transfer restrictions require audit. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed regional agricultural spot/futures prices and water-market transaction history if public reporting is incomplete. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Optional authorized grower exposure/rights, excluded from public work; not obtained. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.
- [Callaway and Sant'Anna, Difference-in-Differences with Multiple Time Periods](https://arxiv.org/abs/1803.09015) — Verified paper title/authors and identification assumptions; does not validate proposed market applications. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
