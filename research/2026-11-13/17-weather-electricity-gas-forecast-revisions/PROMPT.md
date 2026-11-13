# PROMPT — Weather Forecast Revision as an Electricity-to-Gas Risk Hedge
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-17
CATEGORY: B · Domestic & global markets
GEOGRAPHY: US regional power markets and Henry Hub-linked energy
DECISION: Size gas/power-linked hedges using only prior-issued weather forecasts and expected net-load revisions.
H1: Timestamped forecast *revisions* explain next-session electricity net-load stress better than absolute forecast temperature or seasonal normals.
VARIABLES: r is power balancing authority; revisions use two immutable issue-time snapshots; hedge maps only to liquid related assets with modeled cross-basis.
OBJECTIVE: Revision_r,t = LoadForecast_r,t^(latest issued) - LoadForecast_r,t^(prior issued); Hedge_t=clip(β*Revision_r,t,limits)
DATA: NWS issued and archived forecasts, EIA balancing authority hourly load and generation, power/gas futures settlements and basis.
OBSERVATION_GRAIN: balancing authority × weather forecast issuance × lead hour
DECISION_CLOCK: forecast issuance is the earliest legal decision; never consume later realized weather or EIA actual load before release
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Seasonal degree-day demand regression and absolute temperature forecasts.
CANDIDATE: Net-load forecast-revision elasticity with non-linear stress threshold.
ADVANCED: Probabilistic shortfall-and-constraint model with weather ensemble calibration.
EVAL: load p95 quantile loss, probabilistic calibration, hedge tracking error, net futures carry.
MATERIAL_THREAT: Archive of *historical forecasts as issued* may be inaccessible; today's historical observations are not contemporaneous forecasts.
STOP: Reject if no improvements in forecast quantile loss or hedge after-cost variance over degrees-day baseline.
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
