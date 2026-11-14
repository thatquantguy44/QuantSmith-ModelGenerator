---
name: cash-collateral-reinvestment-runoff
description: "Evaluate Cash-Collateral Reinvestment Liquidity Run-Off Controller with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Cash-Collateral Reinvestment Liquidity Run-Off Controller
## Trigger
Use this skill when researching: **Allocate cash-collateral reinvestment across liquid buckets and pre-fund potential return obligations without sacrificing contractually required safety.** in **US securities lending programs**.

## Inputs
Source/version references and license, decision clock, cash collateral program × reinvestment maturity bucket × business day, the cost model, allowed actions, and study windows. Minimum fields: Loan termination flows; collateral principal; reinvestment settlement and maturity ladders; redemption windows; eligible funds; short-term yields; stress scenarios..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category A · Securities finance.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **Static liquidity buffer plus duration/weighted average life constraints.** on training data with full costs.
6. Define **Conditional run-off survival model combined with stochastic cash-flow gap optimizer.**, plus optional **Distributionally robust multi-period policy with borrower return clustering and fire-sale haircuts.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **99% liquidity shortfall, reinvestment net yield, liquidity carry, stressed liquidations, breach count.** plus capacity and tail risk.
8. Try to falsify: **Reject if stress shortfalls are not reduced by at least 10% without degrading contractual yield or creating maturity breaches.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Return flows may cluster under crises; survivorship of reinvestment balances causes understated withdrawals. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
