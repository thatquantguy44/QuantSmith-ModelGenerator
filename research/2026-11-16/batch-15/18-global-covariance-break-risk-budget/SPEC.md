# Specification — Global Covariance-Break Risk-Budget Controller

**QMG-20261116-18 · B — Domestic/global quant markets · research design, empirical state BLOCKED.**

## Decision and hypothesis

Choose between holding current risk weights and a constrained rebalance when covariance-change evidence exceeds its execution cost. Sequential break detection with a no-trade region lowers realized risk-budget tracking error by at least 15% versus monthly EWMA rebalancing without increasing turnover.

```text
min_(w,v) sum_i W_i*(RC_i(w,Sigma_hat)-v*b_i)^2+lambda*||w-w_prev||_1; RC_i=w_i*(Sigma_hat*w)_i/sqrt(w'Sigma_hat*w), v=sqrt(w'Sigma_hat*w), sum_i w_i=1, 0<=w_i<=cap_i, gross_risk_equivalent_leverage<=L
```

w long-only capital weights in predeclared liquid instruments; b target fractions of portfolio volatility summing to one; v total portfolio volatility; W positive error weights; Sigma_hat covariance estimated only from prior synchronized returns; lambda execution penalty; L gross risk-equivalent leverage if futures used. Change alarm selects a covariance window using past data only. This nonlinear risk-budget objective is not asserted convex; solver local/global status must be reported.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-18-REQ-01 | Ingest instrument x completed local session x common information cutoff | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-18-REQ-02 | Build lag-aware covariance, break statistic and marginal turnover cost | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-18-REQ-03 | Implement baseline: Monthly risk parity using 60-day EWMA covariance and fixed weight caps; compare a simple shrinkage covariance with no break detection. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-18-REQ-04 | Fit/solve Sequential covariance change detector plus shrinkage and cost-aware no-trade bands | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-18-REQ-05 | Evaluate realized risk-contribution tracking error at matched turnover and volatility | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-18-REQ-06 | Produce hold/rebalance research decision, risk-contribution certificate and stale-session report | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-18-NFR-01 | All returns carry local session end and actual receive time; no forward fill across a market closure without a stale flag. |
| QMG-20261116-18-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-18-AC-01 | GO if risk-budget RMSE falls >=15% and turnover does not rise over >=3 held-out regimes and multiple asynchronous-market assumptions; STOP if improvement is due to more leverage, reduced target risk or tuned crisis dates. |
| QMG-20261116-18-AC-02 | Delay Japanese returns one extra session and perturb calendar alignment: claimed benefit should remain directionally stable; future-price replacement must fail an availability assertion. |
| QMG-20261116-18-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Daily index/futures/ETF total returns and FX, point-in-time instrument starts/ends, roll calendars, trading sessions, bid/ask and cost curves. H.15 can support rate diagnostics but is not a global total-return panel. Clock: Decide at 16:30 America/New_York using only completed market sessions and public data received by then; execute each market's next liquid session. Stale Asian observations remain lagged rather than filled with later prices. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Look-ahead session alignment, ETF backfill, futures rolls and survivorship change the correlation structure. Same-day cross-market fills may be economically impossible. Illustrative $100m liquid multi-asset allocation; cap <=1% ADV and add market-specific impact, rolls and FX conversion. Capacity derives from instrument liquidity, not covariance model size. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: Medium-high: sequential decision value of covariance breaks with asynchronous-market controls; stronger novelty than adding a complex covariance estimator alone.
