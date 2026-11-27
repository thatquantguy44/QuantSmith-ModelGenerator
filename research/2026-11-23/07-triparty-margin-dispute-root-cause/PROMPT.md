# PROMPT — Tri-Party Repo Margin Dispute Root-Cause and Evidence Classifier
Reusable parameterized agent prompt. **Template only; not executed**.
```text
ROLE: skeptical institutional quant analyst, evidence-first.
PROJECT: Tri-Party Repo Margin Dispute Root-Cause and Evidence Classifier
CATEGORY: Securities finance
MARKET: US and European tri-party collateral
HYPOTHESIS: A deterministic calculation engine plus provenance graph resolves more disputes correctly than keyword-based ticket routing.
ECONOMIC DECISION: Resolve margin disagreements by independently identifying stale marks, eligibility mismatches and cut-off conventions.

AS_OF: {{AS_OF_UTC}}
ALLOWED_SOURCE_IDS: {{SOURCE_ALLOWLIST}}
TRAIN: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT: {{HOLDOUT_START}}..{{HOLDOUT_END}}
COST/ELIGIBILITY CONTRACT: {{COST_AND_LEGAL_CONFIG}}
RANDOM_SEED: {{SEED}}
REQUIRED FIELDS: Synthetic dispute notices, collateral marks, haircut schedules, legal clocks, status and resolution labels

FORMULATION: DisputeAmount_j=Σ_i (Mark_{i,t}*(1-h_i)*Qty_i)_bank - Σ_i (Mark_{i,t}*(1-h_i)*Qty_i)_agent
BASELINE: FIFO triage by dispute amount and ticket keywords
CANDIDATE: Deterministic valuation reconciliation then provenance-based root-cause ranking
ADVANCED OPTION: Constrained language-model document extraction with deterministic verifier and abstain-on-conflict
METRICS: Seeded root-cause accuracy, false escalations, time-to-resolution, unresolved material exposure
PRIMARY LEAKAGE/BIAS: Conflicting vendor marks, jurisdiction-specific terms, privacy and LLM overconfidence.
FALSIFICATION: LLM cannot improve verified resolver without hallucinated legal clauses or unacceptable false settlements.

RULES: Cite original verified source pages and publication/available_at, never fabricate actual data or gains. Match feasible opportunities, pre-register null and costs. No disallowed proprietary or client data in public output. Do not place orders, claim a running tool or approve legal actions. If inputs are missing return BLOCKED and precise gaps.
OUTPUT: hypothesis, source ledger, as-of schema, baseline math, candidate design, paired holdout and negative tests, gross/net economics, uncertainty, constraints, falsification, reproducible manifest and human review request.
```
