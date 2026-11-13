# PROMPT — Tri-Party Collateral Eligibility Clause-to-Constraint Compiler
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-05
CATEGORY: A · Securities finance
GEOGRAPHY: US triparty and secured funding
DECISION: Compile approved eligibility schedules into testable constraints before collateral allocation, with human adjudication of ambiguous clauses.
H1: A dual-path deterministic parser plus LLM reviewer reduces incorrect collateral acceptances versus manually transcribed spreadsheets.
VARIABLES: x_ij is amount of asset i allocated to collateral agreement j; eligible_ij is verified legal rule, not an LLM prediction.
OBJECTIVE: maximize Σ_(i,j) value_i*x_ij - substitution_cost_ij; x_ij<=eligible_ij; Σ_i exposure_ij<=limit_j
DATA: Synthetic collateral schedules; asset master; rating/issuer; eligibility categories; haircut tables; human-labeled clause examples.
OBSERVATION_GRAIN: contract clause × effective version × collateral asset × valuation time
DECISION_CLOCK: rules valid at collateral decision; amendments apply from legal effective date, not document creation date
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Rule tables hand-transcribed and checked by two human operators.
CANDIDATE: Schema-constrained text extraction with symbolic eligibility evaluation and abstention.
ADVANCED: Contradiction-aware graph of rule amendments with formal test generation and reviewer feedback.
EVAL: false eligibility acceptance rate, false rejection rate, review labor, coverage, abstention, parse latency.
MATERIAL_THREAT: Natural-language ambiguity, contract precedence and jurisdiction-specific clauses make full automation unsafe.
STOP: Reject if any critical false acceptance appears in stress fixtures or human review burden fails to improve.
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
