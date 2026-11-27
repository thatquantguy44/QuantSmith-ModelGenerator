# SPEC — Marginal Initial-Margin Attribution for Repo Netting Sets
**QMG-20261127-08 | A — Securities finance | US cleared repo / approved global netting sets | proposal only**
## Decision and falsifiable hypothesis
Assign portfolio margin costs to strategies without treating gross exposure as actual marginal burden. H1: Coalition attribution reconciles total modeled margin and reduces misranking versus notional allocation on held-out trade additions. H0: no material improvement versus pro-rata gross notional allocation under matched rights, costs and opportunities.

## Formulation
φ_i=E_π[M(S_π∪{i})−M(S_π)], Σ_i φ_i=M(N)−M(∅); M approved margin calculator, S predecessor set. Negative contributions allowed but no cross-netting-set credit.

## Data contract
Grain: legal netting set × trade × approved portfolio snapshot. Fields: trade exposures, margin calculator/version, collateral requirements, legal partitions, realized margin changes. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: snapshot and calculator version known at allocation; never use future netting trades. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement pro-rata gross notional allocation; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement sampled Shapley attribution with reconciliation; compare to baseline and stratified permutation/control variate plus incremental risk budget only after freeze.
- REQ-004 / AC-004: report reconciliation error, holdout marginal-cost error, allocation stability, compute time; require relative error ≤1% reconciliation and ≥10% marginal MAE reduction; no illegal netting.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: empty coalition; hedged negative marginal; isolated netting sets; order invariance.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
black-box margin nonlinearities, allocation instability; hypothetical allocations not actual margin calls. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$175k; annual steady-state net operating benefit before project cost B=$150k; launch lag 7 months, no benefit during lag. Capacity assumption: $300m modeled margin-sensitive inventory equivalent × 5 bps estimated allocation efficiency = $150k/year; attribution itself books no savings. Benefit over 24 months = B×(24−lag)/12=$212.5k; ROI=(benefit−C)/C=+21.4%. Half/base/1.5× benefit sensitivity -39.3%/+21.4%/+82.1%; zero benefit −100%; break-even annual benefit $123.5k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Cooperative game theory and risk attribution.
