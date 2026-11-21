# EVALS — CCP Default-Fund Mutualization Marginal Risk Budget
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: A conservative tail contribution metric improves risk-adjusted clearing exposure allocation against nominal balance or posted-margin controls.
H0: Exposure limit proportional to initial margin only performs no worse than Transparent worst-two-member default waterfall simulator on the same legally feasible historical decisions.
Advanced challenger: Coherent-risk allocation via Shapley/gradient ES under correlated default network scenarios

## Preregistered metrics
tail capital charge, stress shortfall, liquidity buffer usage, net clearing benefit; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Use published CCP rulebooks and dated quantitative disclosures only when released; past final stress reports cannot enter historical decisions early.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_ccp_default_fund_tail_budget_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Actual default fund contributions and replenishment terms may differ from public examples and vary by venue.
- Change baseline to Exposure limit proportional to initial margin only plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No material differentiation in conditional tail loss versus margin-only limits after conservative parameter uncertainty.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Default fund and extra margin liquidity headroom, clearing fees and enforceable contribution caps.
$240k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 11 months; annual gross benefit scenarios $0k / $125k / $325k (downside/base/upside) for the remaining 1.0833333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -43.6% / 46.7%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
