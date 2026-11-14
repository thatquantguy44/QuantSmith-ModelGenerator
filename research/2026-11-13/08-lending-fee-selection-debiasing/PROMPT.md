# PROMPT — Securities-Lending Fee Observability & Selection-Bias Corrector
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-08
CATEGORY: A · Securities finance
GEOGRAPHY: US/global securities lending benchmarks
DECISION: Publish uncertainty-aware fee benchmarks and abstain from quote-setting when selected sample coverage is inadequate.
H1: Explicit observability weighting and partial identification shrink apparent fee benchmark error versus sample-weighted means on contributor holdouts.
VARIABLES: y_i is observed fee; X_i observable security/liquidity/context; propensity weights are estimated from an externally validated sample frame.
OBJECTIVE: mu_hat = Σ_i w_i*y_i/Σ_i w_i; w_i=1/P(observed_i|X_i); report sensitivity to unidentified selection
DATA: Contributed executed fee samples; public security volume/short-interest proxies; locate response metadata; source coverage and revisions.
OBSERVATION_GRAIN: security × lending day × vendor/contributor population
DECISION_CLOCK: benchmark at next published cutoff; never use end-of-day contributions before receipt
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Daily equally weighted or outstanding-value-weighted observed market fees.
CANDIDATE: Doubly robust weighting with overlap and selection-sensitivity intervals.
ADVANCED: Bayesian selection model with unverifiable missing-not-at-random stress bounds.
EVAL: cross-contributor benchmark error, interval coverage, abstention, quote drift, market breadth coverage.
MATERIAL_THREAT: Missing-not-at-random selection cannot be identified from executed loans alone; confidence intervals can be falsely narrow.
STOP: Reject if cross-contributor MAE reduction <10% or intervals under-cover known withheld contributions.
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
