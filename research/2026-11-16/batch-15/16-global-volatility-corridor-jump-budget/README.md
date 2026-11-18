# 16. US–Europe Corridor Variance and Jump-Risk Budget

**QMG-20261116-16 · B — Domestic/global quant markets · Priority 83/100 (editorial judgment)**

**Geography/instruments:** US S&P 500 and euro-area equity index options. **Difficulty:** Very high. **Production feasibility:** Method design only until synchronized licensed option chains and execution costs are secured. **Effort assumption:** Two derivatives researchers plus engineer for 16-24 weeks; data cost and tail sample are material blockers.

## Problem, decision and economic value

A headline implied-minus-realized variance gap can compensate for crash jumps and unhedgeable tails; harvesting it without separating those risks can produce misleading expected carry. **Decision:** Allocate a limited short-corridor-variance risk budget across US and European indices while purchasing a defined tail hedge. Economic value is measured through the declared target and net cost model, not forecast accuracy alone.

**Hypothesis (untested):** A corridor/jump-aware allocation reduces 99% tail loss by at least 15% at equal net carry versus equal-vega short-variance with the same tail-hedge budget.

## Mathematics and decision constraints

```text
max_w E[carry(w)]-lambda*CVaR_99(PnL_loss(w)); corridor_RV=sum_k r_k^2*1{L<S_(k-1)<U}; jump_proxy=RV-bipower; |vega_j|<=V_j, stress_loss<=K, hedge_cost<=H
```

r high-frequency log return; L,U predetermined corridor levels; bipower is a training-fixed continuous-variation estimator; j market; w executable option-strip weights; V vega caps; K stress loss limit; H tail premium budget. Corridor payoff convention must match available instruments; VIX itself is not the trade.

Mathematical conventions: one basis point is 0.0001 of annual rate; dt is the declared year fraction. CVaR_a(L)=min_eta[eta+E[(L-eta)^+]/(1-a)] for loss L and tail level a. Risk/turnover penalties are nonnegative and frozen before holdout; rates, prices, cash and face units must reconcile. All forecasts/expectations are conditional on information available at the decision time. A proposed nonlinear or integer formulation is not asserted convex or globally solved without a solver certificate.

## Data and decision timing

Public index methodology for background, synchronized bid/ask option chains, index/futures returns, expiries, dividends, rates and settlement rules. Intraday sampling and overnight jump handling are fixed before testing. **Grain:** market x option expiry/strike x quote instant plus intraday underlying bars. **Decision clock:** Allocate at a common UTC snapshot when both markets have liquid executable quotes; use prior completed return bars only. Do not pair a European close with later US data as contemporaneous.

Every input carries observed_at, published_at, received_at, available_at=max(published_at, received_at), effective_at, source/version/hash and rights_class. Unknown historical release time is not reconstructed from a present-day file timestamp; use the declared conservative lag or exclude the row. In replay, separate an assumed historical ingestion latency from an actually recorded receive time. Outcomes may arrive later but cannot be features.

## Model comparison and evaluation

- **Credible baseline:** Equal-vega option-strip variance exposure by market with a fixed put-spread tail hedge and identical costs.
- **Suggested candidate:** Semiparametric continuous/jump decomposition and constrained risk-budget allocation.
- **Advanced alternative:** Distributionally robust jump-diffusion option-portfolio optimization.
- **Target:** net option-strip carry and stress/tail loss at fixed hedge premium.
- **Metrics:** net carry, 99% ES, stress gaps, margin liquidity, hedge slippage, vega and Greeks.
- **Pre-registered stop/go:** GO if >=15% ES reduction with mean net carry within 5% of baseline across >=8 years including held-out stress; STOP if benefit fails under doubled option spreads or cannot be implemented by listed strips.
- **Critical negative test:** Insert a large overnight gap with no intraday prints: loss and jump exposure must remain visible; an apparent free option caused by zero/stale bid must be rejected.

Use chronological development/validation/untouched holdout partitions at the native decision frequency, purging the full target horizon and overlapping event groups. Fit transforms, calibration and policy parameters inside training folds. Cluster uncertainty by the economic event/issuer/season, not by repeated rows; preserve disappeared instruments and failed outcomes. Report all candidate variants and correct selection uncertainty. If effective sample size is inadequate, mark BLOCKED rather than lower the gate. Require baseline and candidate to use the same information, risk, liquidity, fees and execution opportunity.

## Capacity and economics

Illustrative $20m capital budget with explicit vega/margin limits, <=1% option-strike volume/open-interest bounds and no unlimited tail-risk assumption. Capacity likely concentrated in a few liquid expiries. Capacity and costs are assumptions until measured at executable sizes. Charge bid/ask, impact, funding, financing/borrow where relevant, settlement costs and the stated operating expense. Double spreads/impact and halve assumed capacity in sensitivity analysis.

**Purely illustrative 24-month ROI; assumptions and arithmetic, not empirical evidence.** USD-equivalent affected exposure $20,000,000; annual net benefit scenarios -25/30/100 bps. Value channel: annual incremental net risk-adjusted utility in cash-equivalent scenario terms versus the baseline; not guaranteed realized P&L. Assume 12 months before benefit starts, 1 benefit-years, zero discounting and no terminal value. Two-year all-in engineering/data/review/maintenance cost C=$240,000; this budget is a planning assumption, not a vendor quote. Trading/operating charges are already deducted from scenario benefits; do not deduct them twice.

| Scenario | Annual net benefit before project cost | 24-month benefit B after launch lag | Net ROI (B-C)/C |
|---|---:|---:|---:|
| Downside | $-50,000 | $-50,000 | -120.8% |
| Base | $60,000 | $60,000 | -75.0% |
| Upside | $200,000 | $200,000 | -16.7% |

Break-even annual benefit after launch = $240,000. Full cost is lost if abandoned before benefit; ROI=-100% then. Negative trading/hedge scenarios can be worse than -100%. Utility or avoided-loss scenarios are not guaranteed cash revenue. Budgets and benefits across projects overlap and must not be summed.

## Research value, risk and novelty

**Academic/publication value:** High methodological potential; a crowded literature means exact corridor and jump novelty needs further review. **Key risk:** Sparse extreme events, stale deep-OTM quotes, mid-price replication and model-selected sampling can manufacture carry. Margin calls and holiday mismatches can dominate option premium.

**Cumulative novelty check:** No archived volatility risk-budget project; distinct from options parity for synthetic borrow because the decision prices cross-market tail-risk consumption rather than financing replication. Checked against all 35 archived idea READMEs on main; this is a scoped comparison, not certification of originality in academic literature or inaccessible archives.

## Source ladder and truth state

## 1. Public/free first

- [Cboe VIX methodology](https://cdn.cboe.com/api/global/us_indices/governance/VIX_Methodology.pdf) — Index methodology; VIX is not an executable corridor-variance quote. Option chains and settlement rules need separate licensing. Retrieval run: 2026-11-17T02:38:22+00:00.

## 2. Commercial/licensed

Licensed US/European options, intraday underlying data and exchange settlement/transaction rights; none acquired. Rights, fees, coverage, historical availability and redistribution are **BLOCKED** until reviewed; no entitlement is implied.

## 3. Private/permissioned only after public feasibility

Optional approved margin and execution accounts; no trading authority. Do not upload these records, extracts, identifiers or research results to this public repository. Public outputs use only permitted aggregate summaries or synthetic fixtures reviewed for disclosure.

## 4. Research background

- [Boyd and Vandenberghe, Convex Optimization](https://web.stanford.edu/~boyd/cvxbook/) — Verified author-hosted textbook. Background for convex relaxations, not evidence of an economic edge or MILP global optimality. Retrieval run: 2026-11-17T02:38:22+00:00.

**Evidence classification:** portal/methodology existence was checked through current public search/retrieval. No data download, license clearance, point-in-time panel, calibrated model, price reaction, realized return or ROI was verified. Public accessibility does not grant blanket redistribution. Links support only the statements attached to them; theoretical papers do not support the new hypothesis.


**Status: DESIGN WRITTEN. Empirical execution, data-rights clearance, package lock, runtime, backtest, shadow trial and production implementation: BLOCKED pending the documented prerequisites. No research model was run.**

## Navigation

[SPEC](SPEC.md) · [PLAN](PLAN.md) · [TASKS](TASKS.md) · [ROADMAP](ROADMAP.md) · [HANDOFF](HANDOFF.md) · [SOURCES](SOURCES.md) · [AGENT](AGENT.md) · [SKILL](SKILL.md) · [PROMPT](PROMPT.md) · [TOOLING](TOOLING.md) · [WORKFLOW](WORKFLOW.md) · [RUNTIME](RUNTIME.md) · [EVALS](EVALS.md)
