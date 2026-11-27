# ROADMAP — India Monsoon Surprise to Food CPI and Local Equity Pricing
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check India Meteorological Department Rainfall Information, India OGD Rainfall History versus exact needed fields: IMD daily district rain, crop sowing weights, RBI CPI release, state-level harvest, NSE sector returns. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `Shock_t=Σ_d CropWeight_d*(Rain_d,t - Normal_d,t); ΔCPI_{t+h}=α+β*Shock_t+γ'Controls_t+ε`, create deterministic fixtures and implement `All-India seasonal rainfall deviation plus autoregressive food CPI`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Hierarchical spatial distributed-lag regression + causal crop weighting`, holdout on available historical timestamps and record CPI MAE, sector neutral-return IC, hit rate net costs, seasonal robustness; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Historical IMD OGD resources lag, crop mix revisions, rainfall not yield and policy interventions.; estimate actual execution Large liquid Indian stocks capacity feasible only with correct foreign-investor access, FX costs and exchange calendars., then decide No incremental holdout inflation forecast or stock-return effect against rainfall benchmark..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $100k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
