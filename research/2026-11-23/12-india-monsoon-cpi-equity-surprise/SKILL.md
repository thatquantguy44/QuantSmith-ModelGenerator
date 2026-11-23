---
name: india-monsoon-cpi-equity-surprise
description: "India Monsoon Surprise to Food CPI and Local Equity Pricing: reproducible, source-timed quantitative research design with independent falsification."
---
# SKILL — India Monsoon Surprise to Food CPI and Local Equity Pricing
## When to use
When evaluating: Time/hedge exposures to monsoon-sensitive consumption and agriculture pricing after publicly available rainfall surprises.

## Preconditions
Source entitlement, as-of clock and accounting convention for IMD daily district rain, crop sowing weights, RBI CPI release, state-level harvest, NSE sector returns; a defined decision and costed baseline.

## Procedure
1. Freeze H1: Rainfall surprises weighted by district crop patterns predict food-CPI subcomponents and cross-sectional consumer equity earnings revisions beyond national rainfall.; define H0 with cost-inclusive `All-India seasonal rainfall deviation plus autoregressive food CPI`.
2. Verify official pages and specific historical source versions. IMD publication timestamp and next-tradable-session; CPI only after official release, no revisions used retroactively.
3. Build deterministic synthetic fixtures including: Historical IMD OGD resources lag, crop mix revisions, rainfall not yield and policy interventions..
4. Implement the baseline before trying `Hierarchical spatial distributed-lag regression + causal crop weighting`.
5. Test `Weather-to-crop graph structural state-space model with uncertainty propagation` only if the simpler candidate survives.
6. Reconstruct economic costs and capacity: Large liquid Indian stocks capacity feasible only with correct foreign-investor access, FX costs and exchange calendars..
7. Report CPI MAE, sector neutral-return IC, hit rate net costs, seasonal robustness plus negative-control confidence bounds.
8. Stop if: No incremental holdout inflation forecast or stock-return effect against rainfall benchmark..
9. Prepare code hash, evidence ledger, and independent human review. No trading.

## Outputs
Proposed `manifest.json`, `source_ledger.json`, `baseline.json`, `candidate.json`, `robustness.md`, `decision.md`.
**These output files do not exist in this specification-only batch.**
## Reusability
Reuse point-in-time source gates, mathematical feasibility, cost contracts and paired economic evaluation; keep india-monsoon-cpi-equity-surprise domain-specific features isolated.
