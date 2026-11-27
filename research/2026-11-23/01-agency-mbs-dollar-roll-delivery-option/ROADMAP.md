# ROADMAP — Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check DTCC FICC Mortgage-Backed Securities Division, DTCC Electronic Pool Notification versus exact needed fields: TBA front/back prices, pools, payups, coupon schedules, specified-pool risk, MBSD netting, EPN eligibility and execution costs. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `min_{q_p>=0} Σ_p q_p*(PoolCarry_p + DeliveryCost_p - RollDrop_p), subject to Σ_p q_p = DeliverableNotional, 0<=q_p<=PoolAvailable_p*Eligible_p`, create deterministic fixtures and implement `Dollar-roll implied financing vs same-tenor generic repo without delivery-option valuation`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Constrained pool-delivery optimizer with observable pool financing carry and roll prices`, holdout on available historical timestamps and record Net financing bps, cheapest-deliverable premium, pre-settlement fail exposure, netted capital and tail regret; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Pool price selection, payup optionality, actual pool availability and post-trade EPN leakage.; estimate actual execution Market depth and eligible pool inventory limit size; include bid/ask, delivery allocations, financing and clearing margin., then decide No stable out-of-sample cost-adjusted advantage over delivery-aware manual baseline at realistic pool eligibility..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $130k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
