# SPEC — Exchange Metals Off-Warrant Inventory and Calendar-Spread Scarcity
**QMG-20261127-16 | B — Domestic/global markets | London Metal Exchange global base metals | proposal only**
## Decision and falsifiable hypothesis
Measure whether off-warrant inventory changes improve near-term metal spread risk versus exchange-visible stocks. H1: Lag-correct off-warrant data reduces 20-day spread forecast MAE by 10% versus on-warrant stock and seasonal controls. H0: no material improvement versus on-warrant stocks and curve momentum under matched rights, costs and opportunities.

## Formulation
s_t=F_near−F_far USD/t; x=Δ log(1+offwarrant tonnes); s_t+h=α+β x_t+γ warranted_t+δ controls; position≤approved liquidity; delayed data tier fixed.

## Data contract
Grain: metal × warehouse region × publication date. Fields: off/on-warrant inventories, cancellations, warehouse movements, futures settlements, financing/storage costs. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: free data only after actual T+3 or current verified delay; paid T+1 separately; execute next quote. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement on-warrant stocks and curve momentum; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement distributed-lag inventory/curve model; compare to baseline and latent location-transfer state model with inventory conservation only after freeze.
- REQ-004 / AC-004: report MAE, curve sign accuracy, net spread P&L, capacity; require ≥10% MAE reduction; positive net spread benefit after storage/roll/fees before trading gate.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: T+3 lag versus T+1 contamination; transfers double counted; contract roll.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
warrant cancellations can be relocation not end demand; data rights and warehouse incentives. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$150k; annual steady-state net operating benefit before project cost B=$90k; launch lag 7 months, no benefit during lag. Capacity assumption: $60m risk sleeve × 15 bps annual net scenario=$90k/year; limit to liquid contract depth. Benefit over 24 months = B×(24−lag)/12=$127.5k; ROI=(benefit−C)/C=-15.0%. Half/base/1.5× benefit sensitivity -57.5%/-15.0%/+27.5%; zero benefit −100%; break-even annual benefit $105.9k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Physical inventory observability and futures scarcity.
