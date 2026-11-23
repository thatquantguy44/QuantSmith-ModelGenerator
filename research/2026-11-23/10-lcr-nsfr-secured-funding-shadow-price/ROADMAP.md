# ROADMAP — Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check BIS Basel III Monitoring Release, Sep 23 2026, OFR US Repo Markets Data Release versus exact needed fields: Public Basel ratio methodology/aggregate trends, synthetic collateral classes, cashflow ladder and legal-entity matrices. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `min_x Σ_i (r_i*x_i + k_i*x_i) subject to HQLA_out/HQLA_in≥LCR_min and ASF(x)/RSF(x)≥NSFR_min, Σ_i x_i≥Need`, create deterministic fixtures and implement `Rank repo offers by quoted rate subject to gross notional limits`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Linear/mixed-integer secured funding allocation with LCR/NSFR dual-price attribution`, holdout on available historical timestamps and record All-in liquidity-adjusted cost, marginal dual price, buffer breaches, sensitivity to rule version; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Entity-specific regulatory implementation and internal forecasts differ; cannot reconstruct actual LCR from public totals.; estimate actual execution Use only approved internal regulatory measures when available; funding choices constrained by entity/collateral eligibility., then decide No cost difference over conservative liquidity-constrained benchmark or unstable/uninterpretable duals..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $120k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
