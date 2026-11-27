# SPEC — Swiss Franc Conditional Safe-Haven Hedge Reliability
**QMG-20261127-13 | B — Domestic/global markets | Switzerland, euro area and global risk portfolios | proposal only**
## Decision and falsifiable hypothesis
Size CHF risk-off hedges conditional on funding and volatility regimes, not intervention dates. H1: Conditional hedge reduces global portfolio expected shortfall 10% relative to fixed CHF hedge at equal carry budget. H0: no material improvement versus fixed CHF allocation with equal carry budget under matched rights, costs and opportunities.

## Formulation
min_z ES_95%(−(r_p+z r_CHF))+cost(z); z bounded, |Δz| turnover constrained, returns in common currency; state estimated only from lagged information.

## Data contract
Grain: currency pair × day × decision timestamp. Fields: CHF exchange rates, policy rates, risk factors, global equity returns, executable FX hedge quotes. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: daily decisions after all required markets close, execute next quote; no revised intervention data. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement fixed CHF allocation with equal carry budget; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement threshold quantile regression on risk-state proxies; compare to baseline and hidden Markov state model with robust scenario hedge only after freeze.
- REQ-004 / AC-004: report expected shortfall, carry, hedge hit rate, turnover; require ≥10% ES improvement at matched carry and acceptable return sacrifice; robust to crisis leave-one-out.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: crisis placebo, asynchronous close, stale rate, one-event dominance.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
safe-haven relation unstable; overlapping global closes and intervention confounding. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$145k; annual steady-state net operating benefit before project cost B=$80k; launch lag 6 months, no benefit during lag. Capacity assumption: $200m risk budget × 4 bps annual hypothetical avoided hedging cost=$80k/year; tail-risk reduction not cash revenue unless monetized. Benefit over 24 months = B×(24−lag)/12=$120.0k; ROI=(benefit−C)/C=-17.2%. Half/base/1.5× benefit sensitivity -58.6%/-17.2%/+24.1%; zero benefit −100%; break-even annual benefit $96.7k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: State-dependent hedge reliability and tail dependence.
