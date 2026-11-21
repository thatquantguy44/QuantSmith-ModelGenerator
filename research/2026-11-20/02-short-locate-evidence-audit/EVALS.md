# EVALS — Reg SHO Locate Evidence and Borrow-Capacity Audit Engine
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Event-sourced evidence reconstruction detects noncompliant or capacity-exhausted locates earlier than end-of-day exception review without excess false rejects.
H0: End-of-day deterministic locate exception SQL rules performs no worse than Typed event-sourcing finite-state verification with causal explainability on the same legally feasible historical decisions.
Advanced challenger: Conformal anomaly scoring for ambiguous evidence routed to human review, never autonomous compliance override

## Preregistered metrics
prevented invalid requests, false blocks, recall error, audit completion time, p99 latency; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Locate documentation and quantity must be timestamped before short sale; revised records cannot retroactively authorize prior orders.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_short_locate_evidence_audit_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Reg SHO exemptions, broker responsibilities and settlement rules require qualified legal interpretation.
- Change baseline to End-of-day deterministic locate exception SQL rules plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** Fails to flag intentionally missing/expired/overused locates on synthetic fixtures or blocks materially more valid trades than comparator.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Low per-request CPU; overhead per manual escalation and strict audit storage/retention authorization.
$120k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $115k / $200k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 43.8% / 150.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
