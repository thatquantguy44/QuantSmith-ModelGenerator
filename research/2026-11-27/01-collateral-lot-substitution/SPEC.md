# SPEC — Collateral Substitution with Discrete Lot Opportunity Costs
**QMG-20261127-01 | A — Securities finance | US Treasury and European sovereign repo | proposal only**
## Decision and falsifiable hypothesis
Release high-opportunity-value pledged lots without increasing coverage breaches. H1: A lot-aware substitution policy cuts total collateral carry and transfer costs by at least 5% against cheapest-eligible-first, with no extra coverage breaches. H0: no material improvement versus cheapest eligible collateral first with same lot and transfer constraints under matched rights, costs and opportunities.

## Formulation
min Σ_i,j c_i x_ij + Σ_i,j k_ij |x_ij−x0_ij|; x integer lots; Σ_i v_i(1−h_ij)x_ij≥R_j; Σ_j x_ij≤I_i. i lot, j obligation, c carry, k transfer, v lot value, h haircut, R required coverage, I inventory.

## Data contract
Grain: lot × obligation × snapshot. Fields: lot size, live eligibility, haircut, encumbrance, transfer fees, cutoffs, available inventory and replacement opportunity cost. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: pre-substitution snapshot; confirm replacement settlement before release; no end-day inventory. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement cheapest eligible collateral first with same lot and transfer constraints; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement integer min-cost assignment with opportunity-cost duals; compare to baseline and rolling stochastic mixed-integer control with replacement failure recourse only after freeze.
- REQ-004 / AC-004: report net USD carry/transfer cost, excess collateral, breach count, solve time; require ≥5% lower matched net cost; zero incremental eligibility or coverage violations; p95 solve time within agreed cutoffs.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: one scarce lot assigned twice; replacement not final; haircut shock; infeasible obligation.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
solver can suggest illegal or unsettled substitution if pending collateral is counted. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$170k; annual steady-state net operating benefit before project cost B=$160k; launch lag 6 months, no benefit during lag. Capacity assumption: Assume $1bn average eligible inventory and 2 bps annual gross opportunity improvement, less $40k transfer overhead; $160k/year net before project costs. Benefit over 24 months = B×(24−lag)/12=$240.0k; ROI=(benefit−C)/C=+41.2%. Half/base/1.5× benefit sensitivity -29.4%/+41.2%/+111.8%; zero benefit −100%; break-even annual benefit $113.3k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Discrete optimization under settlement finality and cost duals.
