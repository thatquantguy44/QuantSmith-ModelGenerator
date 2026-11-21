# EVALS — US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: A vintage-consistent carry decomposition improves matched-duration real-vs-nominal excess-return hedging net of liquidity/rollover costs.
H0: Duration-matched TIPS-minus-nominal bond without CPI-calendar signal performs no worse than Deterministic index-ratio accrual and liquidity-factor attribution on the same legally feasible historical decisions.
Advanced challenger: State-space real/nominal curve with stochastic CPI surprise and inflation floor convexity

## Preregistered metrics
hedge tracking error, information ratio net of costs, index replication error, carry decomposition residual; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Daily index ratios can be forecast only from already published reference CPI; preserve first release and later corrections.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_us_tips_indexation_lag_carry_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Illiquid issue quotations, inflation floor optionality, unrevised CPI data and seasonality overfit.
- Change baseline to Duration-matched TIPS-minus-nominal bond without CPI-calendar signal plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** Improvement vanishes versus a carry-only and time-matched duration hedge after execution spread costs.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Issue-level depth, coupon accrued interest, repo funding, bid-ask, tax and duration hedging constraints.
$135k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $105k / $200k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 16.7% / 122.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
