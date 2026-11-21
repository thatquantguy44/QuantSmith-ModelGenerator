# EVALS — Noncash Collateral Correlation-Cluster Haircut Controller
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Cluster-aware chance constraints produce lower stressed shortfall than sector-flat haircuts at a matched average financing cost.
H0: Uniform issuer/asset-class static haircut performs no worse than Scenario CVaR optimization with issuer cluster caps on the same legally feasible historical decisions.
Advanced challenger: Distributionally robust ambiguity-set CVaR with wrong-way liquidity correlation

## Preregistered metrics
shortfall ES, collateral usage, haircut turnover, stress exceptions; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Apply only return histories, prices, group linkages and issuer memberships known at the decision timestamp.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_noncash_collateral_cluster_haircuts_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Asset covariance may break exactly when haircuts are needed and public free-float proxies omit liquidation controls.
- Change baseline to Uniform issuer/asset-class static haircut plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** Risk benefit disappears when using stressed-correlation holdouts or violates legal haircut floors.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Financing spread effects, haircuts, asset transfer restrictions, concentration penalties and market impact.
$210k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $145k / $320k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -13.7% / 90.5%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
