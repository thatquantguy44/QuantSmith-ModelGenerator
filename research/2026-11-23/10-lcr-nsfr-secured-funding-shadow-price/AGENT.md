# AGENT — Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral
**Agent name:** `qmg-lcr-nsfr-secured-funding-shadow-price-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `Dual-priced LCR/NSFR constraints reorder feasible funding selections and improve all-in liquidity-adjusted economics versus spread ranking.` for the economic decision: Allocate financing transactions by incremental liquidity-ratio headroom consumption, not only nominal repo spread.. Geography: Global banks; US/EU Basel liquidity reporting frameworks. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: Public Basel ratio methodology/aggregate trends, synthetic collateral classes, cashflow ladder and legal-entity matrices.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `All-in liquidity-adjusted cost, marginal dual price, buffer breaches, sensitivity to rule version`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: cvxpy, pyomo, scipy, pydantic. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and Entity-specific regulatory implementation and internal forecasts differ; cannot reconstruct actual LCR from public totals. trigger human escalation.
**Escalation:** No cost difference over conservative liquidity-constrained benchmark or unstable/uninterpretable duals..
Public repo may contain synthetic fixtures and verified official links only.
