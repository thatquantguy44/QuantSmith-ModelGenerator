# EVALS — Asia–US Cross-Listed ADR Opening Auction Information Transfer
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: An asynchronous local-information estimator reduces US ADR opening-price execution error beyond last local close plus FX conversion.
H0: Last home close × publicly known ADR conversion ratio × contemporaneous FX spot performs no worse than State-space asynchronous Kalman fair-value update using futures and related peer prices on the same legally feasible historical decisions.
Advanced challenger: Continuous-time latent-price discovery with joint jump and optimal execution inventory control

## Preregistered metrics
auction fair-value error, paired realized slippage, inventory risk, settlement/convertibility feasibility; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Prevent local-price forward fill across sessions; ratio/corporate actions must be known at the US quote decision time.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_asia_us_adr_opening_price_discovery_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- ADR conversion fees, access restrictions, local holidays and stale home quotes create phantom arbitrage.
- Change baseline to Last home close × publicly known ADR conversion ratio × contemporaneous FX spot plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No consistent opening execution improvement after financing, foreign exchange, depositary and auction spread costs.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
ADR opening auction depth, ADR conversion channel capacity, local/US holiday and FX hedging constraints.
$225k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $120k / $310k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -37.8% / 60.7%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
