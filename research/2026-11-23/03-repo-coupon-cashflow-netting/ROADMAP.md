# ROADMAP — Repo Coupon and Principal Event Cash-Flow Netting Scheduler
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check New York Fed Primary Dealer Statistics, SEC EDGAR Data Access versus exact needed fields: Public bond schedules, ex-coupon dates, settlement calendars, synthetic counterparties and netting agreements. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `min_{f_{ij,t},B_t} Σ_t (c_B*B_t+c_F*|f_t|) s.t. Cash_t + B_t + inflow_t - outflow_t ≥0; NettingSet_{ij}=1`, create deterministic fixtures and implement `Gross independent payment processing with static buffer`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Mixed-integer liquidity scheduling with eligibility/netting-set constraints`, holdout on available historical timestamps and record Peak cash buffer, gross payment count, exception cost, settlement timeliness; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Wrong beneficial-ownership treatment, netting rights and special cash settlement terms.; estimate actual execution Savings limited to payments legally eligible for netting; reconciliation costs, daylight overdraft fees and solver latency included., then decide No capacity-adjusted cost reduction versus pre-netted conventional operations or violations of payment rights..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $95k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
