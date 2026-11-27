# SPEC — Accrual Cash-Conversion Reversal with XBRL Restatement Lineage
**QMG-20261127-15 | B — Domestic/global markets | US and foreign SEC reporting equities | proposal only**
## Decision and falsifiable hypothesis
Distinguish operating cash conversion weakness from reporting reclassification before analyst forecast updates. H1: Accession-aware working-capital components reduce next-year cash-flow forecast MAE by 10% versus total accrual ratio. H0: no material improvement versus total accrual ratio plus sector and size under matched rights, costs and opportunities.

## Formulation
A=(NI−CFO)/avg_assets; y=CFO_t+4/assets; y=α+β A+γ ΔAR/assets+δ Δinventory/assets+controls. Units currency matched; signs consistent; no amended values retroactive.

## Data contract
Grain: issuer CIK × fiscal quarter × filing accession × tag. Fields: cash flow, net income, assets, receivables, inventory, restatements, taxonomy mappings and delisting records. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: first filing acceptance/dissemination, with later amended accession separate; decisions next session. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement total accrual ratio plus sector and size; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement sparse panel with accession-aware working-capital features; compare to baseline and hierarchical accounting graph with semantic tag mapping and abstention only after freeze.
- REQ-004 / AC-004: report cash-flow MAE, tag mapping precision, forecast IC, coverage; require ≥10% MAE improvement; ≥98% mapping precision on hand labels; abstain on ambiguity.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: YTD-to-quarter conversion, duplicate tag contexts, unit mismatch, 10-K/A future amendment.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
taxonomy changes, YTD versus quarter flows, acquisition effects, lookahead from amendments. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$115k; annual steady-state net operating benefit before project cost B=$108k; launch lag 4 months, no benefit during lag. Capacity assumption: $90m research sleeve × 12 bps annual net benefit=$108k/year; no measured factor return. Benefit over 24 months = B×(24−lag)/12=$180.0k; ROI=(benefit−C)/C=+56.5%. Half/base/1.5× benefit sensitivity -21.7%/+56.5%/+134.8%; zero benefit −100%; break-even annual benefit $69.0k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Financial statement measurement and reproducible accrual research.
