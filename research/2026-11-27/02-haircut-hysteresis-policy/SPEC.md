# SPEC — Countercyclical Repo Haircut Adjustment with Hysteresis
**QMG-20261127-02 | A — Securities finance | US/EU non-cleared secured funding | proposal only**
## Decision and falsifiable hypothesis
Choose an approved haircut adjustment rule that limits cliff effects while protecting coverage. H1: Hysteresis reduces peak incremental margin liquidity demand by 10% versus rolling-volatility haircuts with no deterioration in closeout tail loss. H0: no material improvement versus rolling volatility haircut with same mandatory floors under matched rights, costs and opportunities.

## Formulation
h_t=max(h_floor,min(h_cap,h_{t−1}+clip(g(z_t)−h_{t−1},−δ_down,δ_up))); z stress, δ approved adjustment caps; compare L=max(E−V_liq,0). Mandatory increases override rate caps.

## Data contract
Grain: collateral class × legal agreement × risk day. Fields: haircut vintages, eligible collateral marks, stress indicators, margin calls and realized liquidation outcomes. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: previously published volatility/rates, signed terms before risk decision. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement rolling volatility haircut with same mandatory floors; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement hysteretic threshold controller; compare to baseline and robust stochastic policy with joint liquidation and funding shocks only after freeze.
- REQ-004 / AC-004: report p99 incremental margin call, expected shortfall of closeout, floor breaches; require ≥10% reduction in p99 call; upper 95% bound for incremental ES≤approved tolerance; zero floor violations.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: mandatory floor jump; fast crash; prohibited haircut decrease.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
selection by counterparty and tail scarcity; slower hikes may worsen credit losses. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$190k; annual steady-state net operating benefit before project cost B=$120k; launch lag 8 months, no benefit during lag. Capacity assumption: Illustrative $400m affected collateral; $120k annual avoided reserve carrying cost at assumed 3% on $4m lower reserve; no credit loss improvement assumed. Benefit over 24 months = B×(24−lag)/12=$160.0k; ROI=(benefit−C)/C=-15.8%. Half/base/1.5× benefit sensitivity -57.9%/-15.8%/+26.3%; zero benefit −100%; break-even annual benefit $142.5k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Control theory for margin procyclicality and stress resilience.
