# ROADMAP — Corporate Bond Securities Lending from CDS Basis Hedge Demand
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check SEC EDGAR Data Access, New York Fed Primary Dealer Statistics versus exact needed fields: CUSIP-level corporate bond lending fees/locates, CDS curves, TRACE trade activity, issue amount, corporate actions. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `E[BorrowDemand_{i,t+1}|F_t]=f(Basis_{i,t},Float_i,Liquidity_{i,t}); max_q Σ_i q_i*(fee_i - failCost_i) with q_i≤available_i`, create deterministic fixtures and implement `Trailing borrower request count and issue-size utilization`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Matched event study plus borrow-arrival hazard conditional on CDS-bond basis`, holdout on available historical timestamps and record Borrow-arrival log score, realized net fee improvement, stale quote rate and borrow supply capacity; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Non-executable CDS quotes, bond TRACE delay and endogeneity of credit distress.; estimate actual execution Bond borrow capacity and transaction costs can overwhelm narrow basis; never equate public volume with tradable borrow., then decide Estimated basis effects fail paired holdouts or increase rejected locates after slippage and liquidity controls..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $110k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
