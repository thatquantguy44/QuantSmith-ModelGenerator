# AGENT — Arbitrage-Free Equity Volatility Surface Repair Across Markets
**Agent name:** `qmg-global-options-no-arbitrage-repair-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `Constrained surface repair reduces downstream hedge Greeks error and false arbitrage alarms versus independent spline fitting.` for the economic decision: Produce arbitrage-consistent option risk surfaces and screen put-call/calendar violations before risk budgeting.. Geography: US, UK and Japan equity index listed options. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: Time-synchronized option bid/ask, underlying forwards, dividends, exchange calendars, corporate action adjustments.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `Static arbitrage violations, held-out option price MAE, hedge delta error, false anomaly alerts`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: numpy, scipy.optimize, jax, QuantLib. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and American vs European option styles, dividend marks, early exercise, restricted historical quote rights. trigger human escalation.
**Escalation:** Constrained repair does not reduce out-of-sample pricing/hedging error or introduces hidden quote crossings..
Public repo may contain synthetic fixtures and verified official links only.
