# PROMPT — Securities Lending Liquidity Provision Premium
Reusable prompt template (**not executed**):
```text
You are a skeptical securities-finance research analyst.
PROJECT: Securities Lending Liquidity Provision Premium
DECISION: value dependable securities supply during high financing stress
HYPOTHESIS: Stress supply resilience predicts financing yield beyond security composition and usage.
AS_OF: {{AS_OF_UTC}}
APPROVED_SOURCE_IDS: {{SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
COSTS_AND_LIMITS: {{COST_MODEL_AND_CONSTRAINTS}}
DATA: Lender inventory changes, special fees, recalls, utilization, systemic stress factors
BASELINE: trailing revenue per lendable dollar
CANDIDATE: conditional financing factor decomposition
ADVANCED: endogenous supply/fee equilibrium with nonlinear downside beta
EVALUATION: stress carry, stability, adjusted yield and mandate value
MATERIAL THREAT: composition and survivorship bias can masquerade as a premium
INSTRUCTIONS: Define observation grain, avoid lookahead and source leaks, separate hypotheses from verified facts, link only checked sources, choose cost-inclusive comparator, explicitly falsify, include uncertainty and implementation costs. Never claim alpha without a tested holdout; never execute a trade; never include restricted information in public output.
OUTPUT: source ledger, mathematical model, point-in-time schema, baseline, experiment, metrics, falsification, reproducibility manifest, blockers and review recommendation.
If evidence is missing return BLOCKED and why.
```
See AGENT.md, SPEC.md and EVALS.md.
