# ROADMAP — Arbitrage-Free Equity Volatility Surface Repair Across Markets
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check Cboe Historical Options Market Statistics, Cboe delayed options data restrictions versus exact needed fields: Time-synchronized option bid/ask, underlying forwards, dividends, exchange calendars, corporate action adjustments. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `min_{σ_surface} Σ_{k,T} w_{k,T}(σ_{k,T}-σ_mid)^2 + λ*Smooth(σ) s.t. ∂_T TotalVar≥0, ConvexCall(K,T)≥0`, create deterministic fixtures and implement `Per-expiry unconstrained cubic interpolation with clip to bid/ask`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Static no-arbitrage SVI/SSVI constrained calibration with conservative quote filters`, holdout on available historical timestamps and record Static arbitrage violations, held-out option price MAE, hedge delta error, false anomaly alerts; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test American vs European option styles, dividend marks, early exercise, restricted historical quote rights.; estimate actual execution Surface repairs support quality/risk decisions first; apparent arbitrage cannot be traded without depth and cost., then decide Constrained repair does not reduce out-of-sample pricing/hedging error or introduces hidden quote crossings..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $105k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
