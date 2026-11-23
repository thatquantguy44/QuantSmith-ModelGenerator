# AGENT — Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization
**Agent name:** `qmg-japan-reit-rate-reset-cashflows-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `Public debt-maturity reset exposure explains post-policy J-REIT return dispersion beyond NAV discount and generic duration beta.` for the economic decision: Distinguish J-REIT rate-reset liability timing and property yield spreads rather than duration-only price sensitivity.. Geography: Japan J-REITs and commercial real estate. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: BOJ rate time series, J-REIT bond/debt disclosures, rent index, total returns and market-based NAV.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `AFFO forecast error, sector-neutral return IC, liquidity-adjusted drawdown, event placebo`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: pandas, polars, statsmodels, pydantic. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and Japanese disclosure translation/lease renewal timing and selective REIT survivorship. trigger human escalation.
**Escalation:** No incremental post-rate-shift forecast after issuer fixed-effects and NAV-duration controls..
Public repo may contain synthetic fixtures and verified official links only.
