# SPEC — Repo RFQ Disclosure-Width versus Execution Competition
**QMG-20261127-07 | A — Securities finance | US and UK institutional repo | proposal only**
## Decision and falsifiable hypothesis
Select an approved RFQ recipient count under information leakage and liquidity constraints. H1: A prespecified randomized recipient-width experiment lowers all-in execution costs versus fixed-width RFQs by 2% with no fill-rate deterioration. H0: no material improvement versus fixed approved number of recipients under matched rights, costs and opportunities.

## Formulation
min_n E[spread(n)×N×τ + impact(n)+message_cost(n)] s.t. n∈approved set, fill≥p_min; N USD, τ year fraction, costs dollars.

## Data contract
Grain: RFQ × recipient-count assignment × session. Fields: RFQ timestamps, eligible recipients, executable responses, trade cost, approved randomization assignment and later price drift. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: assign before outreach; only historical availability and quote freshness; observe outcomes later. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement fixed approved number of recipients; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement randomized experiment and heterogeneous treatment effects; compare to baseline and constrained contextual bandit only after randomized support and approval only after freeze.
- REQ-004 / AC-004: report all-in cost, fill probability, post-RFQ drift, coverage and latency; require ≥2% lower cost, positive paired confidence bound; noninferior fills; zero policy breaches.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: assignment imbalance; correlated RFQs; non-executable response; unsupported recipient.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
interference across simultaneous RFQs and confidential order exposure; observational comparisons biased. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$210k; annual steady-state net operating benefit before project cost B=$150k; launch lag 9 months, no benefit during lag. Capacity assumption: $1bn annual average financed balance equivalent × 1.5 bps net savings = $150k/year; include leakage and message costs. Benefit over 24 months = B×(24−lag)/12=$187.5k; ROI=(benefit−C)/C=-10.7%. Half/base/1.5× benefit sensitivity -55.4%/-10.7%/+33.9%; zero benefit −100%; break-even annual benefit $168.0k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Market microstructure and randomized information design.
