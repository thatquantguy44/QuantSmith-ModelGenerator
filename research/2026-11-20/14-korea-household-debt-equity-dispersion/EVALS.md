# EVALS — Korean Household Debt-Service Shock to Bank–Consumer Equity Spread
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Lag-corrected Korean household DSR changes identify subsequent bank-versus-consumer earnings dispersion beyond policy rates/market beta.
H0: Equal-beta long banks short consumer discretionary with lagged policy-rate signal performs no worse than Panel local projections with shrinkage and sector time fixed effects on the same legally feasible historical decisions.
Advanced challenger: Dynamic heterogeneous household credit impulse response with instrumented policy-rate shocks

## Preregistered metrics
cross-sector earnings forecast delta, beta-neutral IR, worst-regime drawdown, capacity after local spreads; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
BIS Korean DSR published with quarterly lag (available through 2026-Q1 on checked dataset page); do not trade on 2026-Q2 unless publicly released.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_korea_household_debt_equity_dispersion_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Endogenous rate policy and sector composition cause confounding; public issuer histories need delisting continuity.
- Change baseline to Equal-beta long banks short consumer discretionary with lagged policy-rate signal plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No stable expected-earnings or beta-neutral sector difference once rates and economy factors are controlled.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
Local borrow, FX hedge, Korean market access, corporate action history, sector liquidity and taxes.
$170k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $105k / $260k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -22.8% / 91.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
