# AGENT — Chile–Peru Copper Royalty Shock to Sovereign and Mining Credit
**Agent name:** `qmg-latam-copper-royalty-credit-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `Legislated effective marginal royalty changes predict issuer-versus-sovereign credit spread dispersion beyond copper returns.` for the economic decision: Hedge commodity-linked fiscal and issuer credit risk around public mining tax and royalty changes.. Geography: Chile and Peru, mining and sovereign USD/local-currency credit. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: USGS production, government royalty statutes, country budgets, company annual filings, credit spreads and currency.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `Event abnormal spread, FX-adjusted carry, political timing placebo, credit risk attribution`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: statsmodels, linearmodels, pandas, scipy. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and Anticipatory legislative pricing, issuer/sov high correlations, illiquid local bond prices. trigger human escalation.
**Escalation:** No holdout effect after commodity beta and country shock controls or cannot identify legal effective date..
Public repo may contain synthetic fixtures and verified official links only.
