# SPEC — Brazil Reservoir Water Value and Utility Earnings Risk
**QMG-20261127-17 | B — Domestic/global markets | Brazil hydroelectric generation and utility equities | proposal only**
## Decision and falsifiable hypothesis
Estimate shadow water value and thermal substitution cost to stress utility cash flows. H1: Reservoir-aware dispatch simulation improves next-month marginal-cost forecast MAE by 10% versus seasonal reservoir-percentile baseline. H0: no material improvement versus seasonal reservoir percentile and lagged marginal cost under matched rights, costs and opportunities.

## Formulation
V_t=min_g E[Σ c_th g_th+λ EENS+V_{t+1}(S')]; S'=S+inflow−hydro−spill, energy balance Σg≥load, S bounds; quantities MWh, costs BRL.

## Data contract
Grain: ONS subsystem × day × release vintage. Fields: stored energy, inflow, generation, load, thermal costs, transmission constraints, issuer contract exposures. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: only archived public release versions; ONS data may revise; forecast issuance known before decision. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement seasonal reservoir percentile and lagged marginal cost; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement simplified stochastic dispatch LP; compare to baseline and multistage stochastic dual dynamic programming with hydrological scenarios only after freeze.
- REQ-004 / AC-004: report marginal cost MAE, reliability, earnings scenario error, feasible dispatch; require ≥10% forecast MAE improvement; no storage/energy balance violations; pricing claims require market access.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: dry-year holdout, negative storage, future actual inflows, spill.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
physical dispatch simplification, hydrology revision and issuer hedging obscure returns. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$185k; annual steady-state net operating benefit before project cost B=$80k; launch lag 8 months, no benefit during lag. Capacity assumption: $80m utility risk sleeve × 10 bps annual risk improvement=$80k/year; no physical dispatch authority. Benefit over 24 months = B×(24−lag)/12=$106.7k; ROI=(benefit−C)/C=-42.3%. Half/base/1.5× benefit sensitivity -71.2%/-42.3%/-13.5%; zero benefit −100%; break-even annual benefit $138.8k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Stochastic resource control and power-linked equity risk.
