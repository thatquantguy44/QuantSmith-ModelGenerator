# SPEC — US Mortgage Origination Fall-Through and Rate-Lock Convexity
**QMG-20261127-19 | B — Domestic/global markets | US residential mortgage origination and rates | proposal only**
## Decision and falsifiable hypothesis
Improve pipeline hedge sizing by estimating application fallout sensitivity to rate moves. H1: Competing-risk fallout forecasts reduce hedge error 10% against fixed pull-through assumptions on approved lock-level histories. H0: no material improvement versus fixed pull-through by stage and loan type under matched rights, costs and opportunities.

## Formulation
H_t=Σ_i N_i p_i(t) DV01_i; choose hedge z minimizing E[(H_tΔy+zΔF)^2]+cost(z), p pull-through, DV01 dollar per bp; z bounded by mandate.

## Data contract
Grain: application/lock × decision date; public HMDA annual cohort only. Fields: loan outcomes, rates, application attributes, actual lock time, lock rate/expiry, hedge prices. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: public HMDA only after annual release; private locks timestamped before hedge; no demographic targeting. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement fixed pull-through by stage and loan type; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement competing-risk duration model with rate gap; compare to baseline and joint hazard and convexity hedge with correlated fallout scenarios only after freeze.
- REQ-004 / AC-004: report hedge error, pull-through calibration, bias, cost and residual duration; require ≥10% hedge RMSE reduction at equal costs; no use of protected attributes for decisions.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: withdrawals, lock extension, refi regime, future rate and applicant privacy.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
HMDA lacks lock-level timestamps; public model cannot establish live hedge efficacy. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$170k; annual steady-state net operating benefit before project cost B=$100k; launch lag 8 months, no benefit during lag. Capacity assumption: $100m average rate-locked pipeline × 10 bps hypothetical annual hedge improvement=$100k/year. Benefit over 24 months = B×(24−lag)/12=$133.3k; ROI=(benefit−C)/C=-21.6%. Half/base/1.5× benefit sensitivity -60.8%/-21.6%/+17.6%; zero benefit −100%; break-even annual benefit $127.5k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Survival models for mortgage origination convexity.
