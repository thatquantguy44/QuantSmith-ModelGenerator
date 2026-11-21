# EVALS — Japan FX Intervention Impact and Option-Skew Persistence
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: A release-time-corrected intervention-event measure predicts conditional 1–20-day FX variance/skew adjustment beyond macro announcements and momentum.
H0: Standard spot momentum and monetary-policy announcement dummy performs no worse than Disclosure-timestamp event study with matched controls and local projections on the same legally feasible historical decisions.
Advanced challenger: Partial-identification causal synthetic control separating information, execution and portfolio-flow channels

## Preregistered metrics
incremental forward skew/vol forecast skill, delta-hedged net P&L, placebo events, risk-adjusted drawdown; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
MOF 2026 Q3 intervention details published Nov 9, 2026; never use ex-post intervention date labels in same-day live-time signals.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_japan_fx_intervention_persistence_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Actual intervention execution is not transparently known in real time; small event count undermines causal certainty.
- Change baseline to Standard spot momentum and monetary-policy announcement dummy plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No differential response versus rate/central-bank news controls on withheld intervention disclosures or net-option-cost results.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Executable FX spot/options spreads, liquidity, event jump exposure, market access and derivatives capital.
$180k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 8 months; annual gross benefit scenarios $0k / $95k / $240k (downside/base/upside) for the remaining 1.3333333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -29.6% / 77.8%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
