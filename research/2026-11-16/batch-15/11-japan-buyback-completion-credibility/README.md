# 11. Japan Buyback Completion Credibility

**QMG-20261116-11 · B — Domestic/global quant markets · Priority 92/100 (editorial judgment)**

**Geography/instruments:** Japan listed equities; developed-market event research. **Difficulty:** Medium. **Production feasibility:** Public filing pilot feasible; investable panel requires historical prices and delisted firms. **Effort assumption:** One equity researcher and one Japanese-filings engineer for 8-12 weeks.

## Problem, decision and economic value

An announced repurchase ceiling is neither executed demand nor a permanent reduction in free float; completed, cancelled and reissued shares have different effects. **Decision:** Weight an announcement-event equity sleeve by ex-ante completion probability rather than headline authorized buyback size. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** Completion-weighted signals improve 60-trading-day sector/beta-neutral net returns by at least 50 bps per annum versus authorization-size signals, after 30 bps round-trip costs.

## Mathematics and decision constraints

```text
p_i=P(completion_i>=0.8*authorization_i by expiry|X_at_announcement); s_i=p_i*authorized_value_i/float_cap_i; max_w s'w-lambda*w'Sigma*w-k*||w-w_prev||_1; sum w=0, beta'w=0, |w_i|<=0.02
```

i announced program; X includes previously filed completion history, cash constraints and program terms; p calibrated probability; s expected completion intensity; w portfolio weights; Sigma lag-only covariance; k transaction charge. Announced future execution never enters X.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Public issuer/EDINET buyback announcements and monthly completion filings, JPX procedures, cancellation/reissue terms, sector/free-float history, delisted returns and licensed executable prices. J-Quants Pro is a licensed convenience, not assumed free bulk access. **Grain:** issuer x announced buyback program x filing acceptance event. **Decision clock:** Enter at next Tokyo session VWAP after a public announcement plus 30 minutes processing; filings arriving after the next-open cutoff shift another session. Completion reports update only when publicly filed.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Authorization divided by contemporaneously known float market cap, with the same neutral portfolio and execution rules.
- **Suggested candidate:** Calibrated discrete-time completion hazard with constrained event portfolio.
- **Advanced alternative:** Joint competing-risk completion/cancellation model and doubly robust announcement event analysis.
- **Target:** program completion probability and 60-day residual equity return.
- **Metrics:** Brier score, calibration, residual net return, turnover, drawdown, participation and exposure neutrality.
- **Pre-registered stop/go:** GO if completion Brier improves >=10% and net return uplift >=50 annualized bps with block-bootstrap lower bound >0 over >=200 programs and a held-out year; STOP on missing delistings or gains concentrated in inaccessible prints.
- **Critical negative test:** Shift completion filings to their reporting-period end: leakage checker must reject the join; include terminated programs and delisted issuers with zero future authorization assumed.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $25m beta-neutral sleeve; cap each trade at 1% of lagged ADV, use local spreads, impact and shorting costs. Thin small-cap programs may have little scalable edge. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $25,000,000; annual net benefit scenarios -10/50/120 bps. Value channel: annual incremental net residual return over the authorization-only sleeve after trading/borrow/hedge costs. Assume 6 months before benefit starts, 1.5 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$150,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $-25,000 | $-37,500 | -125.0% |
| Base | $125,000 | $187,500 | 25.0% |
| Upside | $300,000 | $450,000 | 200.0% |

Break-even annual benefit after launch = $100,000. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** High: completion credibility and execution mechanism heterogeneity; causal claims require stronger identification than prediction. **Key risk:** Completion is endogenous to stock prices, governance changes and earnings; predictive results do not establish buyback causation. Current issuer lists produce survivorship bias.

**Cumulative novelty check:** No archived buyback-completion project; distinct from the prior AI-capex factor and stock-loan corporate-action economics because the target is equity return after corporate capital-allocation disclosures. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [JPX own-share acquisition procedures](https://www.jpx.co.jp/english/equities/trading/own-company-shares/) — Repurchase mechanisms; does not prove future completion of an announced program. Retrieval run: 2026-11-17T02:38:22+00:00.
- [FSA EDINET API documentation](https://disclosure2dl.edinet-fsa.go.jp/guide/static/disclosure/WEEK0060.html) — Official document API specifications; access registration and historical coverage require implementation checks. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed Japan total-return/delisting panel and optionally J-Quants Pro filings; redistribution not authorized. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Optional privately approved execution logs; unnecessary for a first public/synthetic study. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Callaway and Sant'Anna, Difference-in-Differences with Multiple Time Periods](https://arxiv.org/abs/1803.09015) — Verified paper title/authors and identification assumptions; does not validate proposed market applications. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
