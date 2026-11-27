# SPEC — China Developer Presale Cash-Conversion and Completion Risk
**QMG-20261127-18 | B — Domestic/global markets | China property developers and Asian credit | proposal only**
## Decision and falsifiable hypothesis
Estimate completion funding gap using presales versus construction progress to support credit risk monitoring. H1: Presale funding-gap features improve next-two-quarter distress Brier score 10% beyond leverage and sales growth. H0: no material improvement versus leverage and sales growth hazard under matched rights, costs and opportunities.

## Formulation
G_t=max(0,c·A_unfinished−cash_eligible−ρ·presale_receipts); c cost per sqm, A unfinished area, ρ legally usable receipt fraction; aggregate proxy separate from issuer model.

## Data contract
Grain: developer × reporting quarter / national monthly release. Fields: sales floor area, deposits/advance receipts, completed/started floor area, issuer cash and debt, escrow restrictions. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: first NBS report and issuer filing dissemination, convert cumulative series only using same vintage. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement leverage and sales growth hazard; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement stock-flow gap and competing-risk survival; compare to baseline and hierarchical partially identified funding gaps with escrow scenarios only after freeze.
- REQ-004 / AC-004: report distress Brier, calibration, completion error, uncertainty width; require ≥10% Brier improvement; no future completion data; abstain for unidentified issuer cash availability.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: cumulative reset January, revised comparable basis, negative cash, delisted issuers.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
national aggregate cannot be attributed to specific developers; offshore/onshore exposure and escrow uncertain. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$165k; annual steady-state net operating benefit before project cost B=$120k; launch lag 7 months, no benefit during lag. Capacity assumption: $100m credit risk sleeve × 12 bps annual avoided-loss scenario=$120k/year, not observed default savings. Benefit over 24 months = B×(24−lag)/12=$170.0k; ROI=(benefit−C)/C=+3.0%. Half/base/1.5× benefit sensitivity -48.5%/+3.0%/+54.5%; zero benefit −100%; break-even annual benefit $116.5k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Partial identification of construction funding stress.
