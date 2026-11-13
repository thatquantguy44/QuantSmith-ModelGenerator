# PROMPT — US–Euro Sovereign Curve Shock Decomposition with Data Vintages
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-13
CATEGORY: B · Domestic & global markets
GEOGRAPHY: United States and euro area
DECISION: Allocate DV01-neutral rates hedge exposure between US and European curve tenors after releases, subject to actual market liquidity.
H1: Vintaged macro-announcement decomposition reduces out-of-sample cross-market duration hedge error versus rolling beta.
VARIABLES: y is sovereign yield; Surprise is actual release minus consensus known beforehand (consensus may require licensing); h is DV01-scaled hedge.
OBJECTIVE: Δy_US,t = β1*Surprise_US,t + β2*Surprise_EU,t + u_t; h*=argmin_h E[(ΔP_US+h*ΔP_EU)^2]+turnover_cost(h)
DATA: ECB published euro yield curve, US yields and ALFRED macro vintages, official release times, FX hedges, rates futures cost.
OBSERVATION_GRAIN: economic release event × curve tenor × publication instant × geography
DECISION_CLOCK: end-of-release or next-session decision after releases disseminate; avoid falsely assuming instant access to revised series
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: 60-day rolling DV01-neutral cross-market beta hedge.
CANDIDATE: Vintaged announcement factor model plus shrinkage hedge weights.
ADVANCED: Hierarchical structural yield-curve state-space with distinct real-rate and term-premium factor loading.
EVAL: OOS hedging variance reduction, implementation shortfall, tail DV01 loss, signal turnover.
MATERIAL_THREAT: Public releases cannot recreate market consensus surprises without a licensed historical consensus dataset or explicit no-consensus baseline.
STOP: Reject if hedge variance does not improve at least 5% net of turnover on independent event holdout.
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
