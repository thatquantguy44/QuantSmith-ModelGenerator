# SPEC — Collateral FX Mismatch Hedge under Margin Revaluation
**QMG-20261127-09 | A — Securities finance | USD/EUR/GBP securities finance | proposal only**
## Decision and falsifiable hypothesis
Choose a permissible FX hedge size for existing collateral exposure in another currency. H1: Tail-sensitive FX hedge reduces 10-day margin-call ES by 10% versus static full hedge net of hedge costs. H0: no material improvement versus static full currency hedge with same collateral and limits under matched rights, costs and opportunities.

## Formulation
min_z ES_α([E−V·X+z(X−X0)]^+)+κ|z|; E domestic obligation, V foreign collateral units, X domestic FX, z short foreign units, κ cost; enforce limits and mandatory haircuts.

## Data contract
Grain: collateral basket × currency pair × margin day. Fields: contract currency, collateral value, FX quotes, hedge instruments, margin frequency, hedge liquidity and constraints. Each record requires stable key, effective_at, published_at, available_at, received_at, source/version, units and license class. Timing: only FX quotes/eligibility known before margin and hedge cutoff; hedge at next executable quote. Keep corrected records as new vintages; do not backfill decision-time inputs.

## Requirements and acceptance
- REQ-001 / AC-001: reconstruct valid decision states with the specified grain and source clocks; reject unavailable fields.
- REQ-002 / AC-002: implement static full currency hedge with same collateral and limits; validate economic units and opportunity set on synthetic fixtures.
- REQ-003 / AC-003: implement scenario expected-shortfall hedge sizing; compare to baseline and multi-period robust hedge with FX/collateral joint tails only after freeze.
- REQ-004 / AC-004: report margin call ES, hedge slippage, capital/FX residual, hard constraints; require ≥10% lower ES with total costs reported, no legal/floor violations.
- NFR-001 / AC-005: enforce deterministic inputs, costs and negative tests: FX gap, stale collateral quote, hedge illiquidity, mandatory haircut unchanged.
- NFR-002 / AC-006: legal limits, no restricted publication, no automatic trade or deployment.

## Risk
hedges may not qualify as collateral or reduce regulatory haircut; joint FX/security tails unstable. No-go if gate fails or confidence interval does not establish economically meaningful superiority. **Illustrative 24-month scenario (USD thousands; not empirical ROI):** assumed total build/data/maintenance cost C=$180k; annual steady-state net operating benefit before project cost B=$120k; launch lag 8 months, no benefit during lag. Capacity assumption: $150m affected currency exposure × 8 bps annual risk-buffer cost reduction = $120k/year after hedge fees. Benefit over 24 months = B×(24−lag)/12=$160.0k; ROI=(benefit−C)/C=-11.1%. Half/base/1.5× benefit sensitivity -55.6%/-11.1%/+33.3%; zero benefit −100%; break-even annual benefit $135.0k. No actual adoption, market capacity, realized P&L or cash savings established; validate opportunity overlap and costs before business case.
Publication question: Joint FX collateral tail-risk hedging.
