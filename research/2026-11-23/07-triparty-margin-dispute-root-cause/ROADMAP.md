# ROADMAP — Tri-Party Repo Margin Dispute Root-Cause and Evidence Classifier
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check OFR US Repo Markets Data Release, BIS Basel III Monitoring Release, Sep 23 2026 versus exact needed fields: Synthetic dispute notices, collateral marks, haircut schedules, legal clocks, status and resolution labels. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `DisputeAmount_j=Σ_i (Mark_{i,t}*(1-h_i)*Qty_i)_bank - Σ_i (Mark_{i,t}*(1-h_i)*Qty_i)_agent`, create deterministic fixtures and implement `FIFO triage by dispute amount and ticket keywords`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Deterministic valuation reconciliation then provenance-based root-cause ranking`, holdout on available historical timestamps and record Seeded root-cause accuracy, false escalations, time-to-resolution, unresolved material exposure; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Conflicting vendor marks, jurisdiction-specific terms, privacy and LLM overconfidence.; estimate actual execution Operational capacity limited by manual reviewer; never auto-settle margin on agent output., then decide LLM cannot improve verified resolver without hallucinated legal clauses or unacceptable false settlements..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $110k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
