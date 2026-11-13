---
name: global-equity-dynamic-fx-hedge
description: "Evaluate Dynamic Currency-Hedge and Rebalancing Tax for Global Equity with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Dynamic Currency-Hedge and Rebalancing Tax for Global Equity
## Trigger
Use this skill when researching: **Allocate country equity exposures and currency forward hedge ratios jointly under leverage, country, counterparty and capital-control constraints.** in **US, Japan, euro area, UK and selected liquid EM equity markets**.

## Inputs
Source/version references and license, decision clock, country equity market × FX forward tenor × monthly rebalance date, the cost model, allowed actions, and study windows. Minimum fields: Country index total returns, currency spot/forward curves, FX liquidity, investability restrictions and funding rates..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category B · Domestic & global markets.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **50% static currency hedges plus equal-risk country weights and quarterly turnover.** on training data with full costs.
6. Define **Robust covariance and transaction-cost-aware FX hedge optimizer.**, plus optional **Distributionally robust conditional hedge allocation with Markov stress regime and partial hedging.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **after-cost drawdown, lower-tail CVaR, rolling correlation, FX hedge turnover and volatility.** plus capacity and tail risk.
8. Try to falsify: **Reject if lower-tail risk not improved by at least 5% net of forward carry and turnover without violating return floor.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Country index histories have vendor survivorship and free-float methodological changes; FX pricing may be unavailable at allocated size. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
