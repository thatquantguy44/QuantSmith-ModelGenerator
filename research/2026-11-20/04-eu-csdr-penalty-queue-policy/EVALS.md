# EVALS — European CSDR Penalty-Aware Settlement Queue Prioritization
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: A rule-aware queue policy lowers expected daily penalties and fail duration without worsening operational priority controls relative to FIFO.
H0: FIFO or largest-notional-first allowed settlement priority performs no worse than Constrained weighted-shortest-processing-time queue policy with eligibility rules on the same legally feasible historical decisions.
Advanced challenger: Approximate dynamic programming under stochastic matched delivery arrival times

## Preregistered metrics
penalty liability, fail-days, priority-rule violations, operational throughput; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Penalty exclusions and rules must reflect versions legally in force before each instruction decision; ESMA technical advice is not automatically operative law.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_eu_csdr_penalty_queue_policy_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Misclassification of non-attributable fail causes or legal exclusion yields incorrect optimized queues.
- Change baseline to FIFO or largest-notional-first allowed settlement priority plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No statistically measurable improvement in held-out synthetic and later approved settlement scenarios under equal capacity.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Settlement bandwidth/available inventory and mandatory processing priority; adverse-penalty reallocations cannot violate service commitments.
$145k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 7 months; annual gross benefit scenarios $0k / $100k / $250k (downside/base/upside) for the remaining 1.4166666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -2.3% / 144.3%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
