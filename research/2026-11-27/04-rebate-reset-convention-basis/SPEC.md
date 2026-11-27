# SPEC — Benchmark Reset Convention Basis in Securities Loan Rebates
**QMG-20261127-04 | A — Securities finance | USD and GBP cash-collateral lending | proposal only**
## Decision and falsifiable hypothesis
Quantify mismatch between contractually specified rate resets and cash-investment accruals before renewals. H1: Contract-clock replication explains at least 95% of synthetic/confirmed rebate mismatch and reduces unexplained realized basis versus same-day-rate treatment. H0: no material improvement versus same-day benchmark with standard day count under matched rights, costs and opportunities.

## Formulation
B=Σ_d N_d Δ_d [r_asset(d)−r_rebate(g(d))−s_d]; N notional, Δ contractual year fraction, g maps accrual date to authorized fixing, s fees; respect lookback, holiday and rounding.

## Data contract
Grain: contract × accrual date × fixing vintage. Fields: rate benchmark vintages, executed convention text, spread, calendars, balance and asset accruals. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: fixings available only after publication; project unknown future rates as scenarios, never realized inputs. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement same-day benchmark with standard day count; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement deterministic reset/compounding convention engine; compare to baseline and scenario curve and hedge sensitivity under competing reset clocks only after freeze.
- REQ-004 / AC-004: report reconciliation USD, residual basis, projected mismatch, fixture accuracy; require 100% golden convention fixtures and ≥95% explained confirmed discrepancies; no unexplained sign errors.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: weekend accrual, leap day, missing fixing, negative rate, different day counts.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
ambiguous fallback language and publication lag; legacy terms not inferable from index name. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$100k; annual steady-state net operating benefit before project cost B=$150k; launch lag 4 months, no benefit during lag. Capacity assumption: $500m average balance × 3 bps annual preventable basis = $150k/year; no speculative trading profits. Benefit over 24 months = B×(24−lag)/12=$250.0k; ROI=(benefit−C)/C=+150.0%. Half/base/1.5× benefit sensitivity +25.0%/+150.0%/+275.0%; zero benefit −100%; break-even annual benefit $60.0k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Reproducible multi-calendar accrual microstructure.
