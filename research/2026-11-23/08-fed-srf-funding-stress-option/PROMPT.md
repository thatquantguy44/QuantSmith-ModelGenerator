# PROMPT — Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal
Reusable parameterized agent prompt. **Template only; not executed**.
```text
ROLE: skeptical institutional quant analyst, evidence-first.
PROJECT: Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal
CATEGORY: Securities finance
MARKET: US overnight secured funding
HYPOTHESIS: Publication-aligned SRF utilization and awarded-rate dispersion improve next-session funding stress classification beyond SOFR-GC spread alone.
ECONOMIC DECISION: Monitor time-lagged facility usage and infer when broad repo funding stress warrants buffer review.

AS_OF: {{AS_OF_UTC}}
ALLOWED_SOURCE_IDS: {{SOURCE_ALLOWLIST}}
TRAIN: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT: {{HOLDOUT_START}}..{{HOLDOUT_END}}
COST/ELIGIBILITY CONTRACT: {{COST_AND_LEGAL_CONFIG}}
RANDOM_SEED: {{SEED}}
REQUIRED FIELDS: Official SRF accepted/submitted quantities, summary rates, SOFR, OFR cleared/triparty repo aggregates

FORMULATION: P(Stress_{t+1}=1|F_t)=logit^{-1}(β0+β1*SRFAward_t+β2*RateDisp_t+β3*SOFRSpread_t)
BASELINE: SOFR-GC spread threshold with no SRF information
CANDIDATE: Event-conditioned calibrated logistic hazard with lag-safe publication ledger
ADVANCED OPTION: Structural real-option exercise mapping latent facility usage and dealer cash constraints
METRICS: Brier score, AUPRC, stress false alarm, lead-time, calibrated probability
PRIMARY LEAKAGE/BIAS: SRF operational parameter changes, known policy regime shifts, lack of entity-level same-day data.
FALSIFICATION: No holdout information gain after timing correction, or false positives overwhelm funding buffer costs.

RULES: Cite original verified source pages and publication/available_at, never fabricate actual data or gains. Match feasible opportunities, pre-register null and costs. No disallowed proprietary or client data in public output. Do not place orders, claim a running tool or approve legal actions. If inputs are missing return BLOCKED and precise gaps.
OUTPUT: hypothesis, source ledger, as-of schema, baseline math, candidate design, paired holdout and negative tests, gross/net economics, uncertainty, constraints, falsification, reproducible manifest and human review request.
```
