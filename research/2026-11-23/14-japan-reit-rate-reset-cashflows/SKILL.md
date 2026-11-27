---
name: japan-reit-rate-reset-cashflows
description: "Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization: reproducible, source-timed quantitative research design with independent falsification."
---
# SKILL — Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization
## When to use
When evaluating: Distinguish J-REIT rate-reset liability timing and property yield spreads rather than duration-only price sensitivity.

## Preconditions
Source entitlement, as-of clock and accounting convention for BOJ rate time series, J-REIT bond/debt disclosures, rent index, total returns and market-based NAV; a defined decision and costed baseline.

## Procedure
1. Freeze H1: Public debt-maturity reset exposure explains post-policy J-REIT return dispersion beyond NAV discount and generic duration beta.; define H0 with cost-inclusive `Market REIT index duration and price-to-NAV score`.
2. Verify official pages and specific historical source versions. Use release/filing acceptance before BOJ event and timestamp debt disclosure versions.
3. Build deterministic synthetic fixtures including: Japanese disclosure translation/lease renewal timing and selective REIT survivorship..
4. Implement the baseline before trying `Disclosure-derived maturity-wall factor with event-based hedged return regressions`.
5. Test `Tenant lease rollover and financing reset structural cash-flow model` only if the simpler candidate survives.
6. Reconstruct economic costs and capacity: J-REIT constituent liquidity, FX hedge and foreign-investor restrictions limit realized capacity..
7. Report AFFO forecast error, sector-neutral return IC, liquidity-adjusted drawdown, event placebo plus negative-control confidence bounds.
8. Stop if: No incremental post-rate-shift forecast after issuer fixed-effects and NAV-duration controls..
9. Prepare code hash, evidence ledger, and independent human review. No trading.

## Outputs
Proposed `manifest.json`, `source_ledger.json`, `baseline.json`, `candidate.json`, `robustness.md`, `decision.md`.
**These output files do not exist in this specification-only batch.**
## Reusability
Reuse point-in-time source gates, mathematical feasibility, cost contracts and paired economic evaluation; keep japan-reit-rate-reset-cashflows domain-specific features isolated.
