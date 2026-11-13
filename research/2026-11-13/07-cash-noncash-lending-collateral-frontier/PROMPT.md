# PROMPT — Cash versus Noncash Loan-Collateral Economic Frontier
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-07
CATEGORY: A · Securities finance
GEOGRAPHY: US and international agent lending
DECISION: Price and select borrower-offered collateral methods within owner mandate and agent legal permission.
H1: An all-in haircut, rebate and risk-adjusted price frontier improves loan profitability versus fee-only collateral preference.
VARIABLES: j denotes a feasible collateral convention; values must use common horizon and comparable currency-adjusted cash flows.
OBJECTIVE: max_(j∈allowed) [borrow_fee_j + permissible_reinvestment_yield_j - rebate_j - liquidity_cost_j - expected_loss_j - capital_j]
DATA: Cash and noncash terms, rebate schedules, reinvestment constraints, asset eligibility, mark-to-market, haircuts and legal restrictions.
OBSERVATION_GRAIN: loan offer × collateral type × owner mandate × quotation timestamp
DECISION_CLOCK: quote acceptance before loan opening with known collateral terms, not end-of-day realized earnings
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Choose the highest headline loan spread among eligible offers.
CANDIDATE: Loan-specific all-in economic break-even and constraints solver.
ADVANCED: Robust multi-asset collateral frontier with convex liquidity tail-risk charge.
EVAL: net economic revenue, risk capital per dollar, haircuts and eligibility breaches, retained lending volume.
MATERIAL_THREAT: Comparing unavailable cash reinvestment yield to executable noncash economics creates phantom spread.
STOP: Reject if no incremental cost-adjusted profit after retaining legally admissible and service-quality constraints.
OUTPUT: Claim ledger, source snapshots, math/units, schema, baseline,
candidate, falsification table, full cost/risk sensitivity,
implementation tasks, human decision memo and reproducibility envelope.
RULES:
- Facts need dated primary sources; distinguish fact, computation,
  model inference, unverified hypothesis and counterfactual assumption.
- Never use unavailable macro revisions or post-decision market prices.
- Never leak any customer, position, RFQ, restricted document or secret.
- Stop and report BLOCKED rather than fabricate sources or results.
- No trading, automatic merging or claim of runtime deployment.
```

For inputs and failure behavior consult [AGENT](./AGENT.md) and [SKILL](./SKILL.md).
