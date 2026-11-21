# EVALS — Public BDC Portfolio Fair-Value Markdown Lead Indicator
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Public issuer-level BDC portfolio mark dispersion identifies future credit event/downgrade risk after controlling for BDC leverage and macro credit spread.
H0: BDC aggregate NAV discount and published nonaccrual percentage performs no worse than Issuer-level mark-hazard panel with censored holdings and missing-not-at-random controls on the same legally feasible historical decisions.
Advanced challenger: Hierarchical Bayesian marked-to-market credit migration model with portfolio network dependence

## Preregistered metrics
future credit-event AUC/PR, mark-calibration error, NAV stress accuracy, opportunity capacity; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Use filed investment schedules only after filing acceptance; amendments/revised portfolio marks cannot enter historical quarters.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_us_bdc_private_credit_marks_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- BDC portfolio company identities, valuation methods and distressed sales are not uniformly disclosed; matching bias.
- Change baseline to BDC aggregate NAV discount and published nonaccrual percentage plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No improvement over current NAV discount/nonaccrual baseline in later quarters or effects only known after financial reports.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
BDC equity market depth, credit hedging basis, optional loan trading access and stale valuation discounts.
$190k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $115k / $275k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -29.4% / 68.9%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
