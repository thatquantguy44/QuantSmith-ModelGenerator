# AGENT — Corporate Bond Securities Lending from CDS Basis Hedge Demand
**Agent name:** `qmg-corporate-bond-cds-basis-borrow-demand-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `CDS-bond basis dislocations predict incremental observable bond borrowing demand after conditioning on issue float, liquidity and credit stress.` for the economic decision: Allocate bond lending supply to CDS-bond basis hedging demand with counterparty and liquidity limits.. Geography: US and European investment-grade / high-yield credit. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: CUSIP-level corporate bond lending fees/locates, CDS curves, TRACE trade activity, issue amount, corporate actions.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `Borrow-arrival log score, realized net fee improvement, stale quote rate and borrow supply capacity`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: polars, statsmodels, lifelines, cvxpy. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and Non-executable CDS quotes, bond TRACE delay and endogeneity of credit distress. trigger human escalation.
**Escalation:** Estimated basis effects fail paired holdouts or increase rejected locates after slippage and liquidity controls..
Public repo may contain synthetic fixtures and verified official links only.
