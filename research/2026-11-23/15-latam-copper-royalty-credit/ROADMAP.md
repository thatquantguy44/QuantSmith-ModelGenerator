# ROADMAP — Chile–Peru Copper Royalty Shock to Sovereign and Mining Credit
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check USGS Mineral Commodity Summaries 2026 dataset, SEC EDGAR Data Access versus exact needed fields: USGS production, government royalty statutes, country budgets, company annual filings, credit spreads and currency. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `ΔSpread_{i,t+h}=β*Exposure_i*ΔRoyaltyRate_t+θ*ΔCopperPrice_t+γ'X_i,t+ε`, create deterministic fixtures and implement `Copper price beta plus sovereign spread changes`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Event study with cross-sectional mine exposure and staggered law timing`, holdout on available historical timestamps and record Event abnormal spread, FX-adjusted carry, political timing placebo, credit risk attribution; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Anticipatory legislative pricing, issuer/sov high correlations, illiquid local bond prices.; estimate actual execution Bid/ask for mining credits and FX may swamp basis; avoid assuming continuous trading around policy announcements., then decide No holdout effect after commodity beta and country shock controls or cannot identify legal effective date..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $95k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
