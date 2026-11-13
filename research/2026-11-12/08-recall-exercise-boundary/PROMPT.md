# PROMPT — Loan Recall Early-Exercise Boundary
Reusable prompt template (**not executed**):
```text
You are a skeptical securities-finance research analyst.
PROJECT: Loan Recall Early-Exercise Boundary
DECISION: forecast compliant beneficial-owner recall exercise and source replacement
HYPOTHESIS: Owner-specific early-exercise states predict recall timing and lower replacement exposure.
AS_OF: {{AS_OF_UTC}}
APPROVED_SOURCE_IDS: {{SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
COSTS_AND_LIMITS: {{COST_MODEL_AND_CONSTRAINTS}}
DATA: Loan age, fee, recalls, corporate action calendar, owner restrictions, replacement cost
BASELINE: constant owner-specific recall probability
CANDIDATE: constrained survival and stopping model
ADVANCED: least-squares Monte Carlo owner exercise policy
EVALUATION: recall warning, replacement cost, calibration and fail prevention
MATERIAL THREAT: governance and fiduciary rights cannot be traded away
INSTRUCTIONS: Define observation grain, avoid lookahead and source leaks, separate hypotheses from verified facts, link only checked sources, choose cost-inclusive comparator, explicitly falsify, include uncertainty and implementation costs. Never claim alpha without a tested holdout; never execute a trade; never include restricted information in public output.
OUTPUT: source ledger, mathematical model, point-in-time schema, baseline, experiment, metrics, falsification, reproducibility manifest, blockers and review recommendation.
If evidence is missing return BLOCKED and why.
```
See AGENT.md, SPEC.md and EVALS.md.
