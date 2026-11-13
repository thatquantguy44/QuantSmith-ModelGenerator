# PROMPT — Dynamic Currency-Hedge and Rebalancing Tax for Global Equity
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-19
CATEGORY: B · Domestic & global markets
GEOGRAPHY: US, Japan, euro area, UK and selected liquid EM equity markets
DECISION: Allocate country equity exposures and currency forward hedge ratios jointly under leverage, country, counterparty and capital-control constraints.
H1: State-adaptive hedging reduces after-cost drawdown without sacrificing a pre-specified return floor relative to 0%, 50% and 100% static hedges.
VARIABLES: w are country equity weights; h_c hedge fractions; ES_95 is expected shortfall; forward carry and bid/ask are charged at actual roll.
OBJECTIVE: min_(w,h) E[(R_equity(w)+R_FX(w,h)-target)^2] + λ*ES_95 + μ*turnover(w,h); 0≤h_c≤hmax_c
DATA: Country index total returns, currency spot/forward curves, FX liquidity, investability restrictions and funding rates.
OBSERVATION_GRAIN: country equity market × FX forward tenor × monthly rebalance date
DECISION_CLOCK: rebalance at scheduled month-end using prior-close prices and then-available forward quotes
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: 50% static currency hedges plus equal-risk country weights and quarterly turnover.
CANDIDATE: Robust covariance and transaction-cost-aware FX hedge optimizer.
ADVANCED: Distributionally robust conditional hedge allocation with Markov stress regime and partial hedging.
EVAL: after-cost drawdown, lower-tail CVaR, rolling correlation, FX hedge turnover and volatility.
MATERIAL_THREAT: Country index histories have vendor survivorship and free-float methodological changes; FX pricing may be unavailable at allocated size.
STOP: Reject if lower-tail risk not improved by at least 5% net of forward carry and turnover without violating return floor.
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
