# SPEC — Repo Maturity Mismatch Early-Warning via Survival Cash Ladders
**QMG-20261127-10 | A — Securities finance | US and European matched-book secured funding | proposal only**
## Decision and falsifiable hypothesis
Forecast replacement funding gaps from conditional rollover survival rather than static maturity mismatch. H1: Survival-weighted cash ladders improve next-five-day liquidity shortfall Brier score by 10% versus contractual-only ladders. H0: no material improvement versus contractual maturity ladder with fixed stress rollover percentage under matched rights, costs and opportunities.

## Formulation
G_h=Σ_i N_i 1{m_i≤h}(1−p_i(h))−Σ_j R_j(h); N due liabilities, m maturity, p conditional rollover probability, R confirmed incoming cash; committed resources alone count toward hard limits.

## Data contract
Grain: repo trade × maturity bucket × daily snapshot. Fields: maturity dates, historical renewals/nonrenewals, counterparty segment, rates, confirmed inflows and cutoff. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: decision before maturity; only renewals confirmed by snapshot; outcomes as labels. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement contractual maturity ladder with fixed stress rollover percentage; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement competing-risk survival and calibrated gap scenarios; compare to baseline and hierarchical regime-dependent survival with correlated nonrenewal only after freeze.
- REQ-004 / AC-004: report Brier score, cash-gap quantile coverage, warning lead time, reserve cost; require ≥10% Brier improvement and adequate 95% gap interval coverage; no uncommitted cash counted as guaranteed.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: no renewals in stress, maturity concentration, missing confirmations.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
censoring of renewals and structural shifts; predicted rollover not assured liquidity. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$145k; annual steady-state net operating benefit before project cost B=$120k; launch lag 6 months, no benefit during lag. Capacity assumption: $4m avoided excess average reserve × 3% net carrying cost=$120k/year; no relaxation of required liquidity. Benefit over 24 months = B×(24−lag)/12=$180.0k; ROI=(benefit−C)/C=+24.1%. Half/base/1.5× benefit sensitivity -37.9%/+24.1%/+86.2%; zero benefit −100%; break-even annual benefit $96.7k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Survival analysis for matched-book cash maturity gaps.
