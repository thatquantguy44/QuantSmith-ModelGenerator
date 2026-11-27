# SPEC — Euro Bank Covered versus Unsecured Refinancing Maturity Wall
**QMG-20261127-14 | B — Domestic/global markets | Euro area bank credit | proposal only**
## Decision and falsifiable hypothesis
Forecast relative refinancing spread and funding maturity gaps from public liability disclosures. H1: Debt maturity and encumbrance measures improve next-quarter refinancing spread MAE by 10% beyond rating and curve factors. H0: no material improvement versus rating, duration and sovereign spread regression under matched rights, costs and opportunities.

## Formulation
Gap_b,h=Σ_{m≤h} debt_b,m−cash_b,h−committed_b,h; Δs_b=α+β Gap_b,h/assets_b+γ encumbrance_b+controls; do not count uncommitted issuance as cash.

## Data contract
Grain: issuer × liability class × reporting vintage. Fields: covered/unsecured maturities, encumbrance, bank filings, issuance prices, curves, rating history. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: filing dissemination before monthly decision; issue prices after actual issuance as outcomes. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement rating, duration and sovereign spread regression; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement panel maturity-wall regression with competing liability type; compare to baseline and structural joint issuance choice and spread state model only after freeze.
- REQ-004 / AC-004: report spread MAE, gap error, coverage, class-adjusted residual; require ≥10% MAE improvement on held-out banks/quarters; signs stable under rate controls.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: no issuance censoring; called debt; revised maturities; currency mismatch.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
ECB aggregates do not establish individual maturity terms; selection into issuance. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$155k; annual steady-state net operating benefit before project cost B=$120k; launch lag 7 months, no benefit during lag. Capacity assumption: $120m credit sleeve × 10 bps net annual risk-selection benefit=$120k/year; no guaranteed liquidity. Benefit over 24 months = B×(24−lag)/12=$170.0k; ROI=(benefit−C)/C=+9.7%. Half/base/1.5× benefit sensitivity -45.2%/+9.7%/+64.5%; zero benefit −100%; break-even annual benefit $109.4k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Debt composition and refinancing frictions.
