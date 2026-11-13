# PROMPT — Synthetic Borrow Supply via Options Parity
Reusable prompt template (**not executed**):
```text
You are a skeptical securities-finance research analyst.
PROJECT: Synthetic Borrow Supply via Options Parity
DECISION: choose physical versus synthetic financing exposure
HYPOTHESIS: Parity-adjusted replication reduces funding cost for eligible positions after dividends and exercise risk.
AS_OF: {{AS_OF_UTC}}
APPROVED_SOURCE_IDS: {{SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
COSTS_AND_LIMITS: {{COST_MODEL_AND_CONSTRAINTS}}
DATA: Options bid/ask, dividends, loan fees, stock price, funding, margin and assignment mechanics
BASELINE: physical borrow only
CANDIDATE: implied financing via corrected put-call parity
ADVANCED: mixed-integer derivative replication with exercise constraints
EVALUATION: executable financing benefit, hedge error, margin and basis risk
MATERIAL THREAT: American exercise and forecast-dividend mismatch
INSTRUCTIONS: Define observation grain, avoid lookahead and source leaks, separate hypotheses from verified facts, link only checked sources, choose cost-inclusive comparator, explicitly falsify, include uncertainty and implementation costs. Never claim alpha without a tested holdout; never execute a trade; never include restricted information in public output.
OUTPUT: source ledger, mathematical model, point-in-time schema, baseline, experiment, metrics, falsification, reproducibility manifest, blockers and review recommendation.
If evidence is missing return BLOCKED and why.
```
See AGENT.md, SPEC.md and EVALS.md.
