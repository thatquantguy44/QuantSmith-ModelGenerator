# PROMPT — Cross-Book Securities Finance Identity Reconciliation Graph
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-10
CATEGORY: A · Securities finance
GEOGRAPHY: US and cross-border securities-finance operations
DECISION: Resolve and quarantine inconsistent identities before financing position, collateral and exposure optimization.
H1: A provenance-aware deterministic graph matcher reduces unresolved break hours and false exposure duplications compared with fuzzy string matching.
VARIABLES: M_ij selects a candidate match between external and canonical records; c_ij is audited mismatch cost with hard ID prohibitions.
OBJECTIVE: min_M Σ_(i,j) c_ij*M_ij + λ*unmatched(M); M_ij∈{0,1}, one-to-one constraints and incompatible identifier rules
DATA: Synthetic records containing lifecycle events, ISIN/CUSIP, product type, settlement date, amount, counterparty alias and amendment chain.
OBSERVATION_GRAIN: source record × canonical candidate × event version × timestamp
DECISION_CLOCK: real-time/overnight reconciliation; no future correction can be applied retroactively to a prior risk snapshot
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Exact ID join plus manually triaged fuzzy-name matches.
CANDIDATE: Bipartite deterministic matching with hard identity constraints and provenance.
ADVANCED: Human-review active-learning on uncertain clusters with error budget and privacy-preserving synthetic tests.
EVAL: false merge rate, unmatched %, time to resolve, duplicate exposure USD, manual review hours.
MATERIAL_THREAT: LLM or probabilistic model can silently merge legally distinct entities or settlement legs.
STOP: Reject if critical false merges exceed zero in labeled holdouts or operations time does not decline.
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
