# SPEC — US Small-Cap ATM Equity Issuance Dilution Hazard
**QMG-20261127-11 | B — Domestic/global markets | US small-cap equities | proposal only**
## Decision and falsifiable hypothesis
Estimate dilution exposure and adjust research risk after publicly disclosed ATM programs. H1: Program-level issuance hazard improves next-quarter dilution prediction by 10% versus cash-runway and size baseline. H0: no material improvement versus cash-runway and market-cap logistic hazard under matched rights, costs and opportunities.

## Formulation
P(Δshares>q|X)=logit^-1(βX), exposure D=issued_shares/pre_issue_shares; q=5% preregistered; only public program size and remaining disclosed capacity; no unreported actual sales.

## Data contract
Grain: issuer CIK × accession × trading day. Fields: 424B prospectuses, 8-K/10-Q share counts, cash burn, issuance disclosures, delisting-adjusted returns. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: first dissemination of each accession, next tradable session; quarter issuance outcomes after filings. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement cash-runway and market-cap logistic hazard; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement survival model with disclosed program capacity and competing financing events; compare to baseline and hierarchical joint issuance-size and event-return model only after freeze.
- REQ-004 / AC-004: report Brier, dilution MAE, event return attribution, false-alert rate; require ≥10% Brier improvement; precision improvement at fixed recall; no surviving-only universe.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: authorization without issuance; reverse split; delisting; duplicate supplement.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
ATM authorization is not execution; reverse splits, delayed quarterly reports and failed issuers. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$130k; annual steady-state net operating benefit before project cost B=$150k; launch lag 5 months, no benefit during lag. Capacity assumption: $100m risk sleeve × 15 bps annual net avoided loss scenario=$150k/year; no alpha assumed measured. Benefit over 24 months = B×(24−lag)/12=$237.5k; ROI=(benefit−C)/C=+82.7%. Half/base/1.5× benefit sensitivity -8.7%/+82.7%/+174.0%; zero benefit −100%; break-even annual benefit $82.1k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Corporate financing hazard and disclosure extraction.
