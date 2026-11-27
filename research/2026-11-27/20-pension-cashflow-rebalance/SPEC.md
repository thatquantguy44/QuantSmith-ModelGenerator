# SPEC — Global Pension Contribution-Aware Rebalancing with Trading Frictions
**QMG-20261127-20 | B — Domestic/global markets | US, UK, Canada and Netherlands institutional allocation | proposal only**
## Decision and falsifiable hypothesis
Use forecast contributions/benefits to rebalance policy weights without unnecessary turnover. H1: Cashflow-aware no-trade bands lower cost 10% versus calendar rebalancing at matched policy tracking risk. H0: no material improvement versus calendar rebalancing with identical cashflow forecast and policy constraints under matched rights, costs and opportunities.

## Formulation
min_w (w−w*)'Σ(w−w*)+λΣ c_i|trade_i|; cash balance Σtrade_i=C_t−B_t; long-only policy bounds; w weights, Σ return covariance, C/B cash contributions/benefits, c costs.

## Data contract
Grain: plan type × asset class × month / public annual country aggregates. Fields: policy weights, cash contributions/benefits, portfolio NAV, returns and executable costs. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: only annual OECD releases for long-run calibration; approved plan cashflows known before month-end decisions. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement calendar rebalancing with identical cashflow forecast and policy constraints; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement convex no-trade-band optimizer; compare to baseline and multi-period stochastic control using uncertain benefit payments only after freeze.
- REQ-004 / AC-004: report net transaction costs, tracking error, liquidity shortfalls, turnover; require ≥10% cost reduction at noninferior tracking risk and zero cash deficits.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: cash outflow shock, policy band breach, zero liquidity, stale NAV.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
OECD aggregates cannot reveal real plan trades; benefit schedules private. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$110k; annual steady-state net operating benefit before project cost B=$100k; launch lag 5 months, no benefit during lag. Capacity assumption: $500m illustrative portfolio × 2 bps annual net turnover savings=$100k/year; no trading strategy alpha. Benefit over 24 months = B×(24−lag)/12=$158.3k; ROI=(benefit−C)/C=+43.9%. Half/base/1.5× benefit sensitivity -28.0%/+43.9%/+115.9%; zero benefit −100%; break-even annual benefit $69.5k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Transaction-cost control under institutional contribution/benefit cash flows.
