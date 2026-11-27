# SPEC — Forward Borrow Capacity Reservation for Committed Term Loans
**QMG-20261127-03 | A — Securities finance | US and European equity stock loan | proposal only**
## Decision and falsifiable hypothesis
Decide how much inventory to reserve against future firm lending commitments versus spot availability. H1: Quantile reservation cuts shortage and lost spot-fee costs by 5% versus fixed reserve percentages. H0: no material improvement versus fixed fraction of expected term draws, subject to same owner rights under matched rights, costs and opportunities.

## Formulation
min_r E[c_s(r−D)^+ + c_f(D−r)^+] with 0≤r≤I−other commitments; r reserved shares, D eligible future term draw, c_s forgone spot dollars/share, c_f replacement/penalty dollars/share.

## Data contract
Grain: security × owner mandate × commitment vintage. Fields: signed term commitments, available shares, draw schedules, spot fees, cancellations, replacement cost. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: at commitment acceptance or daily reserve review; only confirmed mandates and availability. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement fixed fraction of expected term draws, subject to same owner rights; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement newsvendor quantile with censored draws and lead times; compare to baseline and multi-period distributionally robust reservation with scenario owner withdrawals only after freeze.
- REQ-004 / AC-004: report shortage shares, realized reservation cost, service coverage, revenue; require ≥5% lower total cost, no worse fulfillment rate, zero double booking.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: concurrent commitment consumes same shares; owner withdrawal; zero available shares.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
historical accepted demand is selected; inventory cannot be promised against unconfirmed availability. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$180k; annual steady-state net operating benefit before project cost B=$200k; launch lag 6 months, no benefit during lag. Capacity assumption: $250m eligible inventory × 8 bp/year avoided shortage/opportunity costs = $200k/year, after modeled variable frictions. Benefit over 24 months = B×(24−lag)/12=$300.0k; ROI=(benefit−C)/C=+66.7%. Half/base/1.5× benefit sensitivity -16.7%/+66.7%/+150.0%; zero benefit −100%; break-even annual benefit $120.0k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Capacity reservation under competing lending demand.
