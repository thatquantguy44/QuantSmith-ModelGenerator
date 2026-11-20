# EVALS — Wheat Export Inspection Revisions to Global Basis and Calendar Spreads
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Vintage-corrected inspection surprises anticipate regional wheat basis and nearby-deferred spread movements beyond seasonality and WASDE.
H0: Monthly seasonal wheat spread regression using last known WASDE performs no worse than Mixed-frequency distributed-lag export surprise model on the same legally feasible historical decisions.
Advanced challenger: Structural Bayesian crop-flow network with regional stock constraints and censoring

## Preregistered metrics
spread forecast delta, regional basis tracking, net slippage-adjusted hedge P&L, regime robustness; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
USDA dashboard launched Oct 14 2026 and wheat tables updated Nov 12 2026; do not replace historic reports with latest annual revisions.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_global_wheat_export_inspection_basis_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Weekly inspections differ from actual export commitments; Black Sea supply and policy announcements may dominate.
- Change baseline to Monthly seasonal wheat spread regression using last known WASDE plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No predictive improvement after weather, futures calendar effects and contemporaneous official release lags.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
CME wheat futures tick, spread roll, physical basis accessibility and region transport costs.
$175k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $100k / $265k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.6% / 89.3%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
