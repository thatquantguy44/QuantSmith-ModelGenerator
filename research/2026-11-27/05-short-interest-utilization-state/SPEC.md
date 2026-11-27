# SPEC — Short Interest versus Securities Loan Utilization State Decomposition
**QMG-20261127-05 | A — Securities finance | US exchange-listed equities | proposal only**
## Decision and falsifiable hypothesis
Determine when borrow utilization reflects loan-market supply contraction versus directional short demand. H1: Release-aligned short-interest anchors reduce 10-day out-of-sample utilization forecast MAE by 10% versus an autoregression. H0: no material improvement versus autoregression on utilization and market returns under matched rights, costs and opportunities.

## Formulation
U_t=L_t/S_t; Δlog U=Δlog L−Δlog S; latent L demand and S lendable inventory in positive state-space; SI published observation is noisy proxy, not identity.

## Data contract
Grain: issuer × share class × trading day / short-interest publication. Fields: reported SI, lender availability/utilization, corporate actions, lendable supply and fees. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: ingest FINRA publication after 4:40 p.m. ET or later actual receipt; trade next eligible session. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement autoregression on utilization and market returns; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement constrained state-space model with delayed SI observation; compare to baseline and hierarchical particle filter with split-adjusted latent demand/supply regime only after freeze.
- REQ-004 / AC-004: report MAE, calibration, supply/demand label precision on verified events; require ≥10% MAE reduction, bootstrap lower bound positive; abstain when components unidentifiable.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: synthetic split, delayed publication, denominator near zero, shuffled release labels.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
short interest is not total loans, coverage differs by vendor and share class. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$160k; annual steady-state net operating benefit before project cost B=$100k; launch lag 7 months, no benefit during lag. Capacity assumption: $200m addressable repricing inventory × 5 bps net annual improvement = $100k/year; conditional on actual policy benefit. Benefit over 24 months = B×(24−lag)/12=$141.7k; ROI=(benefit−C)/C=-11.5%. Half/base/1.5× benefit sensitivity -55.7%/-11.5%/+32.8%; zero benefit −100%; break-even annual benefit $112.9k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Mixed-frequency latent-state identification in lending markets.
