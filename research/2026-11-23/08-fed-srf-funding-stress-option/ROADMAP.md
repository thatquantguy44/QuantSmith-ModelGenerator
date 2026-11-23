# ROADMAP — Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check NY Fed Standing Repo Facility FAQ, OFR US Repo Markets Data Release, New York Fed Primary Dealer Statistics versus exact needed fields: Official SRF accepted/submitted quantities, summary rates, SOFR, OFR cleared/triparty repo aggregates. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `P(Stress_{t+1}=1|F_t)=logit^{-1}(β0+β1*SRFAward_t+β2*RateDisp_t+β3*SOFRSpread_t)`, create deterministic fixtures and implement `SOFR-GC spread threshold with no SRF information`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Event-conditioned calibrated logistic hazard with lag-safe publication ledger`, holdout on available historical timestamps and record Brier score, AUPRC, stress false alarm, lead-time, calibrated probability; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test SRF operational parameter changes, known policy regime shifts, lack of entity-level same-day data.; estimate actual execution Research output is risk-monitoring, not direct trading opportunity; facility eligibility and costs differ by participant., then decide No holdout information gain after timing correction, or false positives overwhelm funding buffer costs..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $70k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
