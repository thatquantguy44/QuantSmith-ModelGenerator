# EVALS — Canadian Mortgage Renewal Cohorts to Bank Credit-Risk Dispersion
**Evaluation design only; no performance run.**

## Hypothesis and benchmark
H1: Estimated vintage-conditioned payment shock predicts cross-bank loan loss and valuation dispersion beyond level rates and employment controls.
H0: Bank loss sensitivity to national unemployment and policy rate alone performs no worse than Vintage-cohort mortgage reset microsimulation from public aggregates on the same legally feasible historical decisions.
Advanced challenger: Hierarchical hazard model linking repricing, prepayment and issuer loan-level exposures

## Preregistered metrics
future loss forecast gain, bank-spread risk hedging, sensitivity to vintage assumptions, net hedging cost; report units, dispersion, percentile tail, economic materiality, power and uncertainty. A statistical p-value alone is not business value.

## Dataset and leakage plan
Use released monthly tables and historical market expectations before renewal; a 2025 note's projected 2026 payments are scenario assumptions, not observed outcomes.
Train, validation, untouched holdout must be chronologically disjoint; purge outcome overlap and embargo at least target horizon. Freeze source entitlement and revision snapshots before accessing future outcomes. Use actual local market sessions and cash-flow calendars. Report delisted/exited instruments, nontrading days and full-feasible-universe selection.

## Negative tests
- Future disclosure backfill and revised-vintage poisoning; `test_canadian_mortgage_renewal_bank_risk_asof`.
- Cost-free imaginary execution and untradable-market placebo.
- Public aggregate cohorts do not identify each bank's borrower vintage distribution or underwriting quality.
- Change baseline to Bank loss sensitivity to national unemployment and policy rate alone plus matched conservative do-nothing choice.
- Adversarial missing inputs, stale published flags, risk limit and source rights violations.

## Falsification / stop-go
**Reject candidate / BLOCKED:** No cross-bank predictive signal after public loan books and unemployment/rate controls, or estimates too wide to act on.
Any empirical advance requires positive *after-cost* incremental decision value on untouched data, no hard constraints broken, and independent method review. If no executable market data exists, report only monitoring/operational diagnostics with NO P&L claim.

## Capital and value screen
TSX bank/equity/CDS liquidity, CAD FX basis, sector beta hedges and credit market impact.
$160k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 8 months; annual gross benefit scenarios $0k / $105k / $240k (downside/base/upside) for the remaining 1.3333333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -12.5% / 100.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Human shadow approval
All SPEC AC-001..AC-006 pass with actual test logs and independent signoff before nonproduction shadow; no production if false positives, data availability or legal limits are unresolved.
