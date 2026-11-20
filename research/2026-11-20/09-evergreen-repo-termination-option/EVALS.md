# EVALS — Evergreen Repo Early-Termination Optionality Risk Budget
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Notice-option-adjusted funding pricing reduces out-of-sample replacement-cost surprises versus duration-only term curve cost.
H0: Static repo spread plus deterministic notice-day funding reserve performs no worse than Least-squares Monte Carlo for bilateral asymmetric stop decisions on the same legally feasible historical decisions.
Advanced challenger: Nonzero-sum stochastic game with liquidity-dependent termination intensities

## Preregistered metrics
replacement funding loss, option premium calibration, cash-flow stress, tail liquidity gap; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Public repo rates have release lags; exact contract termination rights must be known at contract initiation, not retrofitted.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_evergreen_repo_termination_option_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Non-observed counterparty exercise behavior; public term repo alone does not identify proprietary notice clauses.
- Change baseline to Static repo spread plus deterministic notice-day funding reserve plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** Option charge unstable or no improvement over conservative notice reserve in stress holdouts.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Bilateral notice terms, term borrowing capacity, haircuts and closeout spreads constrain exercise decisions.
$180k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $105k / $270k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -31.9% / 75.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
