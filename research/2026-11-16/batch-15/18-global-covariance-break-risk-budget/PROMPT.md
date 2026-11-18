# Parameterized research prompt — Global Covariance-Break Risk-Budget Controller

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for US, Europe, Japan and liquid EM; equity, rates, FX and commodities.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Choose between holding current risk weights and a constrained rebalance when covariance-change evidence exceeds its execution cost.
Hypothesis: Sequential break detection with a no-trade region lowers realized risk-budget tracking error by at least 15% versus monthly EWMA rebalancing without increasing turnover.
Target/grain: realized risk-contribution tracking error at matched turnover and volatility / instrument x completed local session x common information cutoff.
Decision timing: Decide at 16:30 America/New_York using only completed market sessions and public data received by then; execute each market's next liquid session. Stale Asian observations remain lagged rather than filled with later prices.
Baseline: Monthly risk parity using 60-day EWMA covariance and fixed weight caps; compare a simple shrinkage covariance with no break detection.
Candidate: Sequential covariance change detector plus shrinkage and cost-aware no-trade bands; advanced optional: Distributionally robust risk-budget optimization over post-break covariance ambiguity sets.
Build lag-aware covariance, break statistic and marginal turnover cost. Enforce SPEC requirements and hard constraints.
Run negative test: Delay Japanese returns one extra session and perturb calendar alignment: claimed benefit should remain directionally stable; future-price replacement must fail an availability assertion.
Gate: GO if risk-budget RMSE falls >=15% and turnover does not rise over >=3 held-out regimes and multiple asynchronous-market assumptions; STOP if improvement is due to more leverage, reduced target risk or tuned crisis dates.
Return hold/rebalance research decision, risk-contribution certificate and stale-session report, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: Medium-high: sequential decision value of covariance breaks with asynchronous-market controls; stronger novelty than adding a complex covariance estimator alone. A positive synthetic test cannot establish economic profitability.
