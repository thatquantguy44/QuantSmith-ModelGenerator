# PROMPT — Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-16
CATEGORY: B · Domestic & global markets
GEOGRAPHY: United States investment-grade/high-yield credit; optional Europe comparison
DECISION: Hedge credit ETF risk in periods of underlying bond liquidity deterioration without assuming stale NAV is executable.
H1: Publication-time TRACE liquidity dispersion predicts subsequent ETF tracking instability beyond ETF realized volatility and HY/IG spread levels.
VARIABLES: trade_cost_bond is valid time-matched cost proxy; NAVestimate is vendor methodology-specific, potentially stale and never treated as fillable.
OBJECTIVE: LiquidityDisp_t=Q90(trade_cost_bond,t)-Q10(trade_cost_bond,t); predict |ETFprice_t-NAVestimate_t| with quote-timing controls
DATA: FINRA TRACE public aggregate/trade pages, subscription historical bond records, ETF market prices, NAV timestamps, bond indices, CDX basis.
OBSERVATION_GRAIN: bond × disseminated trade timestamp × ETF NAV publication timestamp
DECISION_CLOCK: end-of-session / next-session ETF risk adjustment only; public aggregate data may not cover security-level historical panel
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: ETF realized volatility and quoted bid-ask spread.
CANDIDATE: Robust bond-liquidity dispersion index and ETF tracking-state model.
ADVANCED: Structural ETF redemption/creation network with dealer intermediation bottlenecks.
EVAL: tracking error forecast, credit tail loss, hedge slippage, redemption-state calibration.
MATERIAL_THREAT: Reported bond prices may be size-capped/delayed; TRACE trade access/licensing varies and NAV can embed stale marks.
STOP: Reject if no incremental tracking error forecast or lower stress drawdown after NAV timestamp normalization and realistic ETF costs.
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
