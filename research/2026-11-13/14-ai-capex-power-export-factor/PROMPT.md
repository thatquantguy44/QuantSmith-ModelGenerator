# PROMPT — AI Infrastructure Capex-to-Power-and-Export Supply Chain Factor
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-14
CATEGORY: B · Domestic & global markets
GEOGRAPHY: United States, Taiwan, South Korea, Singapore and Malaysia
DECISION: Construct capacity-confirmation exposures instead of mechanically buying companies mentioning AI investment.
H1: Public capex-to-power-to-export bottleneck signals predict medium-horizon revisions across semiconductor equipment, utilities and data-center supply chains.
VARIABLES: expected_load and needed_components are explicit assumptions, not observable facts; no inferral of private company data-center locations.
OBJECTIVE: Bottleneck_t = min(grid_capacity_t/expected_load_t, export_supply_t/needed_components_t); signal_i,t=exposure_i*(Bottleneck_t-1)
DATA: SEC EDGAR filed capital expenditure and commitments, EIA power demand/generation, public utility service-area reports, UN Comtrade semiconductor/electrical equipment trade.
OBSERVATION_GRAIN: public company disclosure × filing-time vintage × geography × monthly energy/trade release
DECISION_CLOCK: rebalance monthly after latest public filings, energy updates and international trade release
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: Equal-weight US tech/utility/semiconductor thematic basket with broad market hedge.
CANDIDATE: Supply-chain bottleneck score anchored in publicly observed physical constraints.
ADVANCED: Bayesian uncertainty propagation across disclosed commitments, supply chains and commodity/electricity capacity.
EVAL: sector-neutral residual return, realized earnings revision, stock/industry turnover and capacity sensitivity.
MATERIAL_THREAT: Disclosure boilerplate, future guidance and partial energy-grid footprint can generate strong hindsight mapping bias.
STOP: Reject if holdout earnings-revision association and after-cost portfolio uplift vanish after mega-cap momentum controls.
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
