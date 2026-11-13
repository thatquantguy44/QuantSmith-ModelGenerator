# PROMPT — Treasury Clearing Access-Path & Duplicate-Margin Optimizer
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-01
CATEGORY: A · Securities finance
GEOGRAPHY: United States; cleared cash Treasury and repo
DECISION: Route eligible Treasury financing activity among legally permitted clearing access paths and participant entities while honoring CCP and customer-protection constraints.
H1: Path-aware margin, clearing fees and funding costs change the optimal routing mix and reduce total economically consumed liquidity relative to selecting the lowest quoted repo rate.
VARIABLES: x_p is fraction routed through path p; T is year-fraction tenor; margin, default fund, CCLF and netting effects use validated path-specific rules rather than assumed offsets.
OBJECTIVE: min_(x_p) Σ_p x_p*(rate_p*notional*T + fee_p + margin_carry_p + default_fund_p + cclf_liquidity_p) - verified_netting_benefit(x); Σ_p x_p=1; x_p=0 for ineligible paths
DATA: Eligible trade templates; path availability; historical quote spreads; initial/variation margin stress; capital/CCLF allocation; modeled netting sets; direct/sponsored/agent fees.
OBSERVATION_GRAIN: trade × eligible clearing access path × decision timestamp
DECISION_CLOCK: trade routing decision at quote acceptance; historical public aggregates are lagged and cannot be used as intraday quotes
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Minimize executable repo rate ignoring path-specific costs, after validating that every route is eligible.
CANDIDATE: Mixed-integer convex routing with separate margin, settlement and liquidity shadow prices.
ADVANCED: Stochastic two-stage CCP-margin and default-fund planning with cross-netting robustness.
EVAL: USD all-in funding cost, dollar liquidity encumbrance, margin stress p99, ineligible route count, rejection rate.
MATERIAL_THREAT: Clearing rule exemptions and netting eligibility vary; estimated margin offsets could be nonportable across entities.
STOP: Reject if simulated net savings are below 2 bps of affected financing notional or vanish under independently validated margin rules.
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
