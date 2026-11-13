# PROMPT — Trade-Network Export-Shock Transmission to Equity Sectors
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-11
CATEGORY: B · Domestic & global markets
GEOGRAPHY: US, Mexico, Germany, Japan, Korea, China and ASEAN markets
DECISION: Adjust public-market sector risk or hedges using time-valid trade-network concentration shocks, not a blunt GDP exposure factor.
H1: Lag-aware product-network shocks identify medium-horizon cross-country sector earnings surprises beyond FX and industrial production.
VARIABLES: c is country, k sector, p harmonized product/trade edge, h a preselected post-publication investment horizon.
OBJECTIVE: Shock_(c,k,t)=Σ_p upstream_weight_(c,k,p)*Δexports_(p,t); alpha_(sector,t+h)=β*Shock_available_t - controls
DATA: UN Comtrade reported and partner-reported trade by HS code/month; sector country revenue mix; FX; sector returns and macro controls.
OBSERVATION_GRAIN: reporter × partner × HS code × reference month × publication/availability timestamp
DECISION_CLOCK: monthly after trade report publication and revision; NEVER trade at reference-month timestamp
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Equal-weight country sector allocation with FX and local industrial production controls.
CANDIDATE: Sparse directed trade graph factor with event-lag-aware regressions.
ADVANCED: Causal graph neural propagation with hard release-vintage masking and sector earnings transmission.
EVAL: OOS sector information coefficient, dollar-neutral Sharpe, earnings revision hit rate, turnover and tail loss.
MATERIAL_THREAT: Revisions, late reporters, trade re-exports and mapping HS codes to listed firms can create survivorship and spurious exposure.
STOP: Reject if positive net cross-country IC is not stable in each of two disjoint geographic holdouts or after publication lags.
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
