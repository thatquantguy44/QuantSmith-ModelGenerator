# SPEC — Partial Securities Delivery Allocation under Minimum Lot Rules
**QMG-20261127-06 | A — Securities finance | US and European securities settlement | proposal only**
## Decision and falsifiable hypothesis
Allocate limited deliverable shares across obligations when partial settlement is permitted. H1: Quantity-aware integer allocation reduces weighted unmet shares by 10% versus earliest-deadline full delivery. H0: no material improvement versus earliest-deadline-first full delivery under matched rights, costs and opportunities.

## Formulation
min Σ_j w_j(Q_j−x_j)+Σ_j f_j 1{x_j>0}; 0≤x_j≤Q_j, Σ x_j≤I, x_j multiples of m_j; permission and cutoffs hard. Q required, x delivered, I available, w shortfall cost, f fixed processing cost.

## Data contract
Grain: security × settlement instruction × cutoff snapshot. Fields: remaining obligations, settled inventory, minimum lot, partial permission, costs, deadlines and acknowledgments. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: before each cutoff with confirmed deliverable stock; pending receipts excluded. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement earliest-deadline-first full delivery; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement integer allocation with minimum partial sizes; compare to baseline and two-stage stochastic delivery with confirmed receipts and recourse only after freeze.
- REQ-004 / AC-004: report weighted undelivered shares, net fail fees, message count, missed cutoffs; require ≥10% lower weighted unmet shares and non-increasing net costs; zero impermissible partials.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: lot above remainder; negative inventory; all-or-nothing flag; delayed acknowledgement.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
partial processing overhead and legal restrictions differ by venue. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$125k; annual steady-state net operating benefit before project cost B=$160k; launch lag 5 months, no benefit during lag. Capacity assumption: 40k eligible instructions/year × $4 avoidable weighted cost = $160k/year, after message costs. Benefit over 24 months = B×(24−lag)/12=$253.3k; ROI=(benefit−C)/C=+102.7%. Half/base/1.5× benefit sensitivity +1.3%/+102.7%/+204.0%; zero benefit −100%; break-even annual benefit $78.9k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Discrete resource allocation with settlement microstructure.
