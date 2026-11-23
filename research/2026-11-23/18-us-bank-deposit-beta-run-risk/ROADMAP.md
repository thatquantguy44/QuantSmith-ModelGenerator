# ROADMAP — US Bank Deposit Beta and Mark-to-Market Securities Run Risk
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check FDIC Bank Financial Reports, FRED Data Portal versus exact needed fields: FDIC bank Call Reports, quarterly uninsured deposits, HTM/AFS loss fields, benchmark rates, bank equity CDS. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `NII_i≈Loans_i*r_L - Deposits_i*(r_D0+β_i*Δr) - Wholesale_i*r_W ; StressGap_i=HTMLoss_i+RunOutflow_i*FundingSpread`, create deterministic fixtures and implement `Uninsured deposit share plus book capital ratio`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Hierarchical deposit beta estimation plus accounting-based duration stress`, holdout on available historical timestamps and record Next-quarter NII loss, downside rank precision, capital shortfall, sector-neutral return IC; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Quarterly revisions, mergers, bank survivorship and missing bank-specific deposit pricing.; estimate actual execution Large regional bank equity/cash bonds viable; small banks thin, CDS pricing inaccessible and not required for public proxy., then decide No incremental forecast versus capital/deposit mix baseline after strict public release lag..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $120k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
