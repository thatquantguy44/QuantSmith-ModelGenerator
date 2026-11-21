# EVALS — ETF Creation/Redemption Basket Shock to Stock-Loan Supply
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Point-in-time basket-flow measures predict incremental short-horizon available-to-lend changes beyond conventional index membership and short-interest proxies.
H0: Change in ETF shares outstanding plus index-event dummy performs no worse than Hierarchical event study with issuer-basket aggregation and controls on the same legally feasible historical decisions.
Advanced challenger: Instrumented flow shock model addressing ETF price-demand endogeneity

## Preregistered metrics
inventory forecast MAE, short availability calibration, incremental net inventory carry, execution slippage; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Only baskets available to a decision-maker before ETF order cutoff may be used; end-of-day holding reports are not morning baskets.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_etf_basket_stockloan_flow_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Most executable AP basket details and actual stock-loan supply are not public.
- Change baseline to Change in ETF shares outstanding plus index-event dummy plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No incremental held-out inventory signal after availability alignment and underlying stock flow controls.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Inventory is limited by mandate, lendability and recalls; transaction fees and timing dominate thin basket effects.
$190k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $130k / $280k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -14.5% / 84.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
