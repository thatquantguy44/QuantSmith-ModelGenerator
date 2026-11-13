# PROMPT — Settlement-Fail Buy-In versus Wait Optimal Stopping
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-06
CATEGORY: A · Securities finance
GEOGRAPHY: US Treasury and agency settlement
DECISION: For an already-failed settlement instruction, decide when to cover, reroute or await delivery under documented close-out rules.
H1: A time-to-cure policy using fail penalties and executable cover costs lowers realized failure resolution expense versus fixed escalation cutoffs.
VARIABLES: s contains security, counterparty, days failed, available cover liquidity and contractual remedy state.
OBJECTIVE: V_t(s)=min{cover_cost_t(s), reroute_cost_t(s), fail_penalty_t(s)+E[V_(t+1)(s')|s]}
DATA: Public dealer failure aggregates for calibration; synthetic failure life histories; approved buy-in quotes, fails charges and legal remedies.
OBSERVATION_GRAIN: failed settlement instruction × elapsed failed day × cut-off timestamp
DECISION_CLOCK: business-day cure decisions only after confirmed fail and remedy eligibility
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Auto-escalate after fixed N-day failure age.
CANDIDATE: Discrete-time survival model with exact dynamic-programming stopping rule.
ADVANCED: Partial-observation optimal stopping with supply scarcity and stochastic cover price.
EVAL: resolved failure days, total cure cost, forced buy-in count, missed deadline, tail loss.
MATERIAL_THREAT: Fails charges and rights to enforce buy-ins differ by asset, market and contract; wrong assumptions invalidate decisions.
STOP: Reject if holdout cost savings are below 5% or any mandated deadline is missed.
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
