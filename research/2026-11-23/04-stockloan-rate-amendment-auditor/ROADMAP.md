# ROADMAP — Securities Loan Retroactive Rate Amendment Revenue Assurance
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check SEC EDGAR Data Access, BIS Basel III Monitoring Release, Sep 23 2026 versus exact needed fields: Synthetic loans, amendment lifecycle, dated fee notices, loan terminations, currency and day-count conventions. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `Invoice_i=Σ_{d∈loanlife_i} Principal_{i,d} * Fee_{i,d} * DayFraction_d ; Error_i=Invoice_posted_i-Invoice_authorized_i`, create deterministic fixtures and implement `Latest agreed fee × end-period balance × elapsed days`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Bitemporal finite-state rate and loan lifecycle ledger with invariant checks`, holdout on available historical timestamps and record Synthetic exception precision/recall, manual hours, invoice basis-point leakage, false escalation rate; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Contract-level bilateral waiver rules, fee confirmation ambiguity and out-of-order event feeds.; estimate actual execution Value in avoided losses and less manual rework, not trading alpha; false dispute costs and review minutes cap benefit., then decide No improvement in high-severity seeded exceptions relative to deterministic ledger, or unauthorized dispute actions..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $95k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
