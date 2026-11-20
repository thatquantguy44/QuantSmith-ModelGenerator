# EVALS — Securities-Lending Circular Flow Surveillance via Temporal Graphs
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Causal temporal-motif alerts improve precision at fixed review capacity over pairwise round-trip thresholds in seeded synthetic cases.
H0: Two-party net-quantity turnaround rules performs no worse than Temporal graph motif detection with exact deterministic event identity on the same legally feasible historical decisions.
Advanced challenger: Weakly supervised dynamic graph anomaly ranking with human-in-loop conformal calibration

## Preregistered metrics
precision at K, seeded motif recall, legitimate-flow false-alerts, explanation fidelity; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Create graph only from recorded transfers visible before alert time; disallow knowledge of subsequent investigation outcomes in features.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_seclending_circular_flow_surveillance_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- False accusations, privileged customer data, and severe sample-selection bias in investigated cases.
- Change baseline to Two-party net-quantity turnaround rules plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No precision@K gain against pairwise rules under benign high-volume churn fixtures.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Compliance analyst review capacity and evidentiary retention, no automatic client suspension.
$165k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $95k / $240k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.0% / 81.8%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
