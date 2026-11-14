---
name: cash-noncash-lending-collateral-frontier
description: "Evaluate Cash versus Noncash Loan-Collateral Economic Frontier with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Cash versus Noncash Loan-Collateral Economic Frontier
## Trigger
Use this skill when researching: **Price and select borrower-offered collateral methods within owner mandate and agent legal permission.** in **US and international agent lending**.

## Inputs
Source/version references and license, decision clock, loan offer × collateral type × owner mandate × quotation timestamp, the cost model, allowed actions, and study windows. Minimum fields: Cash and noncash terms, rebate schedules, reinvestment constraints, asset eligibility, mark-to-market, haircuts and legal restrictions..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category A · Securities finance.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **Choose the highest headline loan spread among eligible offers.** on training data with full costs.
6. Define **Loan-specific all-in economic break-even and constraints solver.**, plus optional **Robust multi-asset collateral frontier with convex liquidity tail-risk charge.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **net economic revenue, risk capital per dollar, haircuts and eligibility breaches, retained lending volume.** plus capacity and tail risk.
8. Try to falsify: **Reject if no incremental cost-adjusted profit after retaining legally admissible and service-quality constraints.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Comparing unavailable cash reinvestment yield to executable noncash economics creates phantom spread. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
