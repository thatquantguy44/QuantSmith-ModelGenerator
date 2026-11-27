# AGENT — CCP Member Default Position-Porting Time and Liquidity Optimization
**Agent name:** `qmg-ccp-member-porting-time-risk-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `A capacity-constrained porting algorithm lowers simulated liquidation shortfall and time-to-restore relative to static member choice.` for the economic decision: Choose contingent porting routes and liquidity reserves for a hypothetical clearing-member default.. Geography: Global cleared rates and repo portfolios. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: Public CCP rulebooks; synthetic position/eligibility and margin profiles; simulated member outage.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `Porting completion by deadline, unmet margin, loss given port failure, rerouting overhead`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: ortools, simpy, scipy, networkx. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and Actual CCP porting legality and bilateral customer consents unknown, correlated failures may be unidentifiable. trigger human escalation.
**Escalation:** No improvement in adverse default scenarios over conservative porting alternatives or reliance on forbidden client position data..
Public repo may contain synthetic fixtures and verified official links only.
