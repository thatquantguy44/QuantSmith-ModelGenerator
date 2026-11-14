# PROMPT — Manufactured-Dividend and Corporate-Action Loan Economics
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-03
CATEGORY: A · Securities finance
GEOGRAPHY: US and cross-listed global equities
DECISION: Determine whether a permitted loan extension, pre-event return or alternative allocation is economically superior without compromising beneficial-owner legal rights.
H1: Event-time aware loan optimization removes avoidable payment/operational leakage relative to fee-only renewal rules while remaining faithful to tax/legal restrictions.
VARIABLES: a is a legally permitted loan lifecycle action; each component is booked at the owner-specific event date and in consistent after-tax units.
OBJECTIVE: max_(a in eligible_actions) [fee(a)-manufactured_payment_adjustment(a)-corporate_action_cost(a)-recall_cost(a)-tax_adjustment(a)]
DATA: Ex/record/pay dates; loan life; fee accrual; event elections; dividend amounts; owner tax flags and permitted return/recall rules.
OBSERVATION_GRAIN: security × beneficial owner program × corporate-action event × decision timestamp
DECISION_CLOCK: event decisions before ex-date cutoff, using only announced corporate actions and approved tax interpretations then available
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Renew if lending fee remains positive and return only upon explicit mandatory recall.
CANDIDATE: Rule-checked event economics and constrained loan life-cycle integer optimizer.
ADVANCED: Scenario tree for unresolved election announcements and corporate action adjustment ranges.
EVAL: net program income, missed payment events, operational exceptions, unauthorized action count.
MATERIAL_THREAT: Tax withholding, treaty benefits and manufactured-dividend treatment cannot be assumed from issuer-country information alone.
STOP: Reject if post-cost incremental program income is nonpositive or event-aware policy increases mandatory-payment exceptions.
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
