# Cleared Versus Tri-Party Repo Fragmentation Nowcast
**A · Securities finance** · **Priority 92/100** · **Difficulty Medium** · **Feasibility: High for lagged research signals** · **Publication interest 5/5 (conceptual, not a paper).**

## Why this exists
Aggregate secured funding can conceal diverging clearing venues, tenor demand and collateral composition, delaying recognition of venue-specific stress.

**Market / geography:** United States short-term funding markets. **Asset classes:** OFR cleared repo vs tri-party funding.

## Falsifiable hypothesis and investment/operational decision
A public-data fragmentation state predicts next-session tail moves in funding conditions beyond aggregate SOFR and repo volume.

**Decision:** Adjust next-day funding risk overlays and desk liquidity buffers based on *publication-time* inter-venue segmentation rather than guessed live spreads..

## Research model
```text
F_t=Σ_v ω_v (r_v,t-r_ref,t)^2 + η*HHI(volume_v,t); predict P(stress_(t+1)|F_<=t, publication_lags)
```
v indexes funding venue/tenor/collateral categories; weights ω_v normalize liquidity; η calibrates volume concentration penalty.

## Data and decision clock
OFR cleared and tri-party rate-volume series; collateral categories; SOFR; weekly dealer aggregate financing; release metadata. **Observation grain:** venue × collateral class × tenor × underlying observation date, plus public publication timestamp. **Decision horizon:** risk update only after OFR release; cleared repo T+1 and tri-party T+2 availability; never use same-day unpublished values.

## Baseline versus candidate
- **Baseline:** SOFR level change and aggregate funding volume z-score.
- **Proposed model:** State-space latent fragmentation index with lag-aware missingness.
- **Advanced option:** Hierarchical online change-point and causal regime attribution by venue and reporting channel.
- **Primary metrics:** next-session stress AUPRC, calibrated Brier score, false alarm rate, funding stress drawdown.
- **Falsification:** Reject if lag-safe AUPRC does not exceed SOFR-only benchmark by 0.03 on an untouched crisis/quiet holdout.
- **Primary economic or methodological caveat:** Revised/missing suppressed OFR cells and cross-venue holiday timing can create lookahead and artificial divergences.

## 24-month ROI sensitivity (unverified assumptions only)
USD $125k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $40k–$210k over 24 months. Net ROI = (gross benefit − cost)/cost = **-68% to 68%**. NOT forecast or historical measurement. Economic lever: scenario: avoid one or two large risk-buffer errors or reduce manual funding surveillance effort; no P&L is proven.

## Execution, capacity and feasibility
An alert/risk-overlay product first; any later trade signal faces venue access, funding tenor and prices.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
