# EVALS — Cyber-Outage Contingent Repo Funding Recovery Routes
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Conditional multi-route recovery decreases funding shortfall and expected disruption cost more than an equal-cost static backup buffer.
H0: Fixed 10% contingency funding buffer with one permitted fallback performs no worse than Two-stage robust multi-commodity flow with cyber failure scenarios on the same legally feasible historical decisions.
Advanced challenger: Distributionally robust scenario-tree route control with simultaneous correlated cash-lender disruptions

## Preregistered metrics
shortfall dollars, p95 duration, liquidity carry, fail probability, recovery cost; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
OFR cleared rate/volume normally T+1 and tri-party T+2, so use public series as lagged calibration only; route outage telemetry must be timestamped pre-decision.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_repo_cyber_funding_recovery_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Public aggregates cannot recover the bank-level cash-lender network or prove an actual route is legally available.
- Change baseline to Fixed 10% contingency funding buffer with one permitted fallback plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** Held-out synthetic/approved outage replay fails to reduce mean + tail shortfall at fixed total contingency cost.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Route/credit limits, settlement windows, cleared access and fallback switching charges; no publicly executable orders.
$220k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $180k / $340k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 2.3% / 93.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
