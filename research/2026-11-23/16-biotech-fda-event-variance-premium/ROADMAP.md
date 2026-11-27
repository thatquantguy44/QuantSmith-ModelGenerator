# ROADMAP — Biotech FDA Catalyst Probability versus Options Event Premium
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check openFDA Drugs@FDA, SEC EDGAR Data Access, Cboe Historical Options Market Statistics versus exact needed fields: FDA event dates, approval histories, pre-event public filings, full options surfaces, equity halt and event-time trades. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `ExpectedJumpVar_i=Σ_s p_{i,s}*(log(P_{after,s}/P_before))^2; VRP_i=ImpliedEventVar_i-ExpectedJumpVar_i-Cost_i`, create deterministic fixtures and implement `Historical absolute event returns grouped by market cap and indication`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Regulatory-document event taxonomy + shrinkage conditional jump model`, holdout on available historical timestamps and record Jump variance calibration, option VRP after costs, event coverage, tail hedge error; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test FDA database daily updates can lag original approval; sample selection, delistings and halted option quotes.; estimate actual execution Biotech option spreads and gap risk severe; define small budget and loss limit before evaluating., then decide Conditional probability model fails event-matched calibration or net executable option premium..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $110k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
