# EVALS — SFTR Reporting Regime Drift and Public-Private Divergence Detector
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Joint change-point tests on volumes, missingness and reported collateral taxonomy identify synthetic or historical reporting breaks more reliably than absolute-value outlier rules.
H0: Fixed ±3-sigma z-score alert on each series performs no worse than Robust multivariate Bayesian online change-point detection on the same legally feasible historical decisions.
Advanced challenger: Hierarchical regime/missingness change-point models with document version embeddings as covariates

## Preregistered metrics
break detection delay, false alarms, post-correction economic interpretation stability; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Use publication timestamps and repository versions, not reporting reference dates; detailed transaction data are supervisor-restricted.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_sftr_reporting_regime_drift_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Only public aggregate data may be available, making root-cause verification incomplete.
- Change baseline to Fixed ±3-sigma z-score alert on each series plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** Synthetic change fixtures not detected within agreed delay or false alerts exceed preregistered burden.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Low runtime; review cost per alert and regulator/source availability dominate feasibility.
$135k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $90k / $190k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 0.0% / 111.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
