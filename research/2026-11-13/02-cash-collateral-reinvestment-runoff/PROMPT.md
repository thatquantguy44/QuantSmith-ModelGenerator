# PROMPT — Cash-Collateral Reinvestment Liquidity Run-Off Controller
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-02
CATEGORY: A · Securities finance
GEOGRAPHY: US securities lending programs
DECISION: Allocate cash-collateral reinvestment across liquid buckets and pre-fund potential return obligations without sacrificing contractually required safety.
H1: State-dependent loan run-off and reinvestment ladder simulation lowers liquidity shortfall probability versus static maturity and expected-return assumptions.
VARIABLES: w_k is share in maturity/liquidity bucket k; CVaR_99 is 99% expected shortfall on repayment funding deficits, not investment P&L.
OBJECTIVE: min_w E[funding_cost(w)+liquidity_shortfall_penalty(w)] + λ CVaR_99(shortfall(w)); Σ_k w_k=1; WAM/WAL/eligibility and liquidity floors hold
DATA: Loan termination flows; collateral principal; reinvestment settlement and maturity ladders; redemption windows; eligible funds; short-term yields; stress scenarios.
OBSERVATION_GRAIN: cash collateral program × reinvestment maturity bucket × business day
DECISION_CLOCK: end-of-day reinvestment decision with availability of prior published cash flow and eligible settlement windows
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Static liquidity buffer plus duration/weighted average life constraints.
CANDIDATE: Conditional run-off survival model combined with stochastic cash-flow gap optimizer.
ADVANCED: Distributionally robust multi-period policy with borrower return clustering and fire-sale haircuts.
EVAL: 99% liquidity shortfall, reinvestment net yield, liquidity carry, stressed liquidations, breach count.
MATERIAL_THREAT: Return flows may cluster under crises; survivorship of reinvestment balances causes understated withdrawals.
STOP: Reject if stress shortfalls are not reduced by at least 10% without degrading contractual yield or creating maturity breaches.
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
