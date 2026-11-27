# SPEC — Mexico Nearshoring Realization versus Industrial Equity Expectations
**QMG-20261127-12 | B — Domestic/global markets | Mexico, US–Mexico industrial corridor | proposal only**
## Decision and falsifiable hypothesis
Estimate whether realized factory labor utilization—not announcements—improves industrial cash-flow forecasts. H1: IMMEX hours/employment surprise improves next two-quarter industrial earnings forecast MAE by 10% beyond FX and exports. H0: no material improvement versus FX/export growth plus issuer lagged earnings under matched rights, costs and opportunities.

## Formulation
y_i,t+2=α_i+β_i Σ_r w_ir Δlog(hours_r,t)+γX_t+ε; y earnings growth, w frozen regional exposure, X FX/exports/rates; weights nonnegative sum≤1.

## Data contract
Grain: region × release month × issuer. Fields: IMMEX staffing/hours, issuer geography, earnings, FX, exports, corporate announcements. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: first INEGI monthly release and financial report timestamps, region weights frozen before prediction. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement FX/export growth plus issuer lagged earnings; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement hierarchical exposure-weighted panel forecast; compare to baseline and dynamic factor with announcement-versus-realization measurement error only after freeze.
- REQ-004 / AC-004: report MAE, revision sensitivity, sector-neutral forecast IC; require ≥10% MAE reduction in untouched quarters; no benefit from future region weights.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: future revisions, missing plant map, peso shock, announcement placebo.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
IMMEX program composition shifts; firms disclose incomplete plant geography. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$150k; annual steady-state net operating benefit before project cost B=$80k; launch lag 7 months, no benefit during lag. Capacity assumption: $80m research sleeve × 10 bps annual decision improvement=$80k/year after turnover, capacity unverified. Benefit over 24 months = B×(24−lag)/12=$113.3k; ROI=(benefit−C)/C=-24.4%. Half/base/1.5× benefit sensitivity -62.2%/-24.4%/+13.3%; zero benefit −100%; break-even annual benefit $105.9k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Regional industrial measurement and cross-border fundamentals.
