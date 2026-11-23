# Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal
**ID:** B17-08 · **Group:** Securities finance · **Geography:** US overnight secured funding · **Priority:** 88/100 · **Status:** not implemented

## Economic decision and hypothesis
SRF usage can be distorted by auction mechanics and participants' idiosyncratic conditions, not just aggregate funding scarcity.

**Decision:** Monitor time-lagged facility usage and infer when broad repo funding stress warrants buffer review.

**H1:** Publication-aligned SRF utilization and awarded-rate dispersion improve next-session funding stress classification beyond SOFR-GC spread alone.

## Formulation
```text
P(Stress_{t+1}=1|F_t)=logit^{-1}(β0+β1*SRFAward_t+β2*RateDisp_t+β3*SOFRSpread_t)
```
**Variables:** Stress is pre-defined funding event; F_t contains only SRF summary published by decision time.

**Data:** Official SRF accepted/submitted quantities, summary rates, SOFR, OFR cleared/triparty repo aggregates

**Clock:** Use posted operation result time and repo series 1-2-day publication lags; do not use same-day hidden participant-level bids.

**Baseline:** SOFR-GC spread threshold with no SRF information; **candidate:** Event-conditioned calibrated logistic hazard with lag-safe publication ledger; **advanced:** Structural real-option exercise mapping latent facility usage and dealer cash constraints.

**Evaluation:** Brier score, AUPRC, stress false alarm, lead-time, calibrated probability. **Failure:** No holdout information gain after timing correction, or false positives overwhelm funding buffer costs.

**Capacity:** Research output is risk-monitoring, not direct trading opportunity; facility eligibility and costs differ by participant.

**Illustrative sensitivity:** $115k assumed total 24m development/data/maintenance cost; assumed launch in month 5; assumed annual gross outcome downside/base/upside $0k/$70k/$170k. Resulting 24m net ROI **-100.0% / -3.6% / 134.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
