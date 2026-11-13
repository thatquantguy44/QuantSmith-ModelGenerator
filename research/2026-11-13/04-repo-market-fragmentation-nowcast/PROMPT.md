# PROMPT — Cleared Versus Tri-Party Repo Fragmentation Nowcast
**Parameterized instruction template, not an executed model.**

```text
ROLE: Skeptical, source-grounded institutional quantitative researcher.
ID: QMG-20261113-04
CATEGORY: A · Securities finance
GEOGRAPHY: United States short-term funding markets
DECISION: Adjust next-day funding risk overlays and desk liquidity buffers based on *publication-time* inter-venue segmentation rather than guessed live spreads.
H1: A public-data fragmentation state predicts next-session tail moves in funding conditions beyond aggregate SOFR and repo volume.
VARIABLES: v indexes funding venue/tenor/collateral categories; weights ω_v normalize liquidity; η calibrates volume concentration penalty.
OBJECTIVE: F_t=Σ_v ω_v (r_v,t-r_ref,t)^2 + η*HHI(volume_v,t); predict P(stress_(t+1)|F_<=t, publication_lags)
DATA: OFR cleared and tri-party rate-volume series; collateral categories; SOFR; weekly dealer aggregate financing; release metadata.
OBSERVATION_GRAIN: venue × collateral class × tenor × underlying observation date, plus public publication timestamp
DECISION_CLOCK: risk update only after OFR release; cleared repo T+1 and tri-party T+2 availability; never use same-day unpublished values
AS_OF_UTC: {{AS_OF_UTC}}
ALLOWED_LICENSED_SOURCES: {{APPROVED_SOURCE_IDS}}
TRAIN_WINDOW: {{TRAIN_START}}..{{TRAIN_END}}
HOLDOUT_WINDOW: {{HOLDOUT_START}}..{{HOLDOUT_END}}
RISK_LIMITS: {{POLICY_LIMITS}}
TRANSACTION_COST_CONFIG: {{COST_CONFIG}}
BASELINE: SOFR level change and aggregate funding volume z-score.
CANDIDATE: State-space latent fragmentation index with lag-aware missingness.
ADVANCED: Hierarchical online change-point and causal regime attribution by venue and reporting channel.
EVAL: next-session stress AUPRC, calibrated Brier score, false alarm rate, funding stress drawdown.
MATERIAL_THREAT: Revised/missing suppressed OFR cells and cross-venue holiday timing can create lookahead and artificial divergences.
STOP: Reject if lag-safe AUPRC does not exceed SOFR-only benchmark by 0.03 on an untouched crisis/quiet holdout.
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
