---
name: credit-trace-etf-nav-dislocation
description: "Evaluate Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
## Trigger
Use this skill when researching: **Hedge credit ETF risk in periods of underlying bond liquidity deterioration without assuming stale NAV is executable.** in **United States investment-grade/high-yield credit; optional Europe comparison**.

## Inputs
Source/version references and license, decision clock, bond × disseminated trade timestamp × ETF NAV publication timestamp, the cost model, allowed actions, and study windows. Minimum fields: FINRA TRACE public aggregate/trade pages, subscription historical bond records, ETF market prices, NAV timestamps, bond indices, CDX basis..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category B · Domestic & global markets.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **ETF realized volatility and quoted bid-ask spread.** on training data with full costs.
6. Define **Robust bond-liquidity dispersion index and ETF tracking-state model.**, plus optional **Structural ETF redemption/creation network with dealer intermediation bottlenecks.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **tracking error forecast, credit tail loss, hedge slippage, redemption-state calibration.** plus capacity and tail risk.
8. Try to falsify: **Reject if no incremental tracking error forecast or lower stress drawdown after NAV timestamp normalization and realistic ETF costs.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Reported bond prices may be size-capped/delayed; TRACE trade access/licensing varies and NAV can embed stale marks. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
