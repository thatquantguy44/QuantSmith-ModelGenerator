# AGENT — Borrow Scarcity Causal Effect on Equity Market-Maker Quoted Depth
**Agent name:** `qmg-borrow-scarcity-equity-market-depth-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `Exogenous changes to borrow supply lower subsequent displayed depth/increase effective spreads more than matched control stocks.` for the economic decision: Adjust financing risk capital for equity liquidity provision when short-sale borrow becomes scarce.. Geography: US equities and select developed markets. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: Borrow availability and fees, market quotes/trades, issuer event calendars and exclusion instruments.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `Event-time β confidence interval, placebos, effective spread, depth and incremental risk price`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: linearmodels, statsmodels, polars, econml. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and Selection on distressed shorts, simultaneous volatility and hard-to-borrow endogenous events. trigger human escalation.
**Escalation:** No pre-registered effect with valid pretrends/instruments or effect only on illiquid untradeable names..
Public repo may contain synthetic fixtures and verified official links only.
