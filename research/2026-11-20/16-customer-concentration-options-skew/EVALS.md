# EVALS — Issuer Customer-Concentration Disclosure to Earnings Options Skew
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Point-in-time EDGAR customer concentration disclosures explain forward options downside skew changes beyond leverage, size and event vol.
H0: Size/leverage/industry/earnings event-only option skew estimator performs no worse than Censored-disclosure panel with inverse observation probability adjustment on the same legally feasible historical decisions.
Advanced challenger: Jump-diffusion structural model of concentrated-customer exit hazard

## Preregistered metrics
post-filing skew residual, risk hedge efficiency, delta-neutral net performance and disclosure coverage; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Use SEC acceptance timestamps and first published disclosure, not retroactive tagged XBRL after amended filings.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_customer_concentration_options_skew_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Customer concentrations may be anonymized and nonrandomly omitted; options trade data can be illiquid.
- Change baseline to Size/leverage/industry/earnings event-only option skew estimator plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No post-filing incremental skew or hedge gain beyond conventional earnings-related jump risk.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Option open interest, bid/ask, assignment/maturity mechanics and volatile event hedging friction.
$160k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $85k / $260k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -33.6% / 103.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
