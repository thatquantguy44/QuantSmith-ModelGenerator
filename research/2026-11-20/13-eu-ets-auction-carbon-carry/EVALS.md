# EVALS — EU ETS Auction Supply Revision and Carbon Futures Carry
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Public-vintage auction-volume shocks improve calendar-spread/hedge-risk forecasts beyond front-month momentum and seasonal dummies.
H0: Calendar-month fixed seasonal allowance spread performs no worse than Event study of auction schedule revisions and futures risk factors on the same legally feasible historical decisions.
Advanced challenger: Partial equilibrium allowance banking model with endogenous industrial abatement and policy scenarios

## Preregistered metrics
EUA spread basis MAE, hedged risk reduction, net carry after fees, low-liquidity scenario loss; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
2027 auction schedule announced Jul 30 2026; 2025 compliance data public Oct 5 2026; only released data at as-of permitted.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_eu_ets_auction_carbon_carry_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Policy revision expectations may be priced before official publication; futures/Registry coverage not contemporaneous.
- Change baseline to Calendar-month fixed seasonal allowance spread plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No out-of-sample spread forecast or hedge benefit net of spreads after matched energy factors.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
EUA contract liquidity, expiry rolling, carbon compliance mandates and margin/collateral limits.
$210k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $125k / $310k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -25.6% / 84.5%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
