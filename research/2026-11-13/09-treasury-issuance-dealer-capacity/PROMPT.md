# PROMPT — Treasury Issuance-to-Dealer Intermediation Capacity Map
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-09
CATEGORY: A · Securities finance
GEOGRAPHY: United States issuance and dealer system
DECISION: Set research-level short-term Treasury liquidity stress overlays around security supply events, independent of day-of-quarter calendar effects.
H1: Public auction-supply and weekly dealer-position innovations predict future Treasury liquidity stress more reliably than rate volatility alone.
VARIABLES: C_t is an issuance-absorption mismatch proxy, not observed dealer capital; p is stress probability, h is pre-set future horizon.
OBJECTIVE: C_t=Δissuance_t - β*Δdealer_financed_positions_t; p_(t+h)=sigmoid(α+γ*C_(available≤t)+δ*vol_t)
DATA: Treasury auction issuance and settlement schedule; weekly primary dealer net positions/financing; OFR repo aggregates; public Treasury yield changes.
OBSERVATION_GRAIN: issuance cohort × week of publicly released dealer aggregates
DECISION_CLOCK: weekly close after primary dealer publication; never treat reported prior-week positions as contemporaneous
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Treasury yield volatility and calendar week indicators.
CANDIDATE: Event-study + state-space dealer supply absorption proxy.
ADVANCED: Instrumented quasi-experiment using prescheduled auction supply shocks and cross-CUSIP constraints.
EVAL: stress forecast Brier, AUPRC, lead-time, false positives and hedge drawdown.
MATERIAL_THREAT: Aggregate dealer reports cannot identify securities or dealers and issuance is endogenous to financing conditions.
STOP: Reject if no improvement over the rate-volatility-only benchmark on genuinely held-out issuance regimes.
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
