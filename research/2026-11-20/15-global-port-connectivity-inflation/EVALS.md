# EVALS — Global Shipping Connectivity Re-Routing to Inflation and Equity Margins
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Route-centrality-adjusted connectivity changes improve delayed goods-inflation and shipper-margin forecasts over raw container volume.
H0: Aggregate global shipping index versus region CPI with fixed lag performs no worse than Supply-route network exposure local projections on the same legally feasible historical decisions.
Advanced challenger: Causal graph shock transmission with endogenous alternative route capacity and measurement error

## Preregistered metrics
inflation nowcast gain, equity margin dispersion, attribution stability and hedged net P&L; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
UNCTAD latest confirmed index data update Sep 28 2026; a 2026-11-20 decision cannot use December data.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_global_port_connectivity_inflation_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Connectivity is not real-time port congestion and quarterly updates can obscure freight cycle timing.
- Change baseline to Aggregate global shipping index versus region CPI with fixed lag plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No incremental signal after global industrial production, oil and published trade volume controls.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Sector ETF/futures depth, global market close mismatch, FX hedge and rebalance slippage.
$220k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $135k / $300k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.4% / 59.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
