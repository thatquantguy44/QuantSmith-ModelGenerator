# ROADMAP — Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check Bank of Japan Time-Series Data Search, SEC EDGAR Data Access versus exact needed fields: BOJ rate time series, J-REIT bond/debt disclosures, rent index, total returns and market-based NAV. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `CashInterest_{i,t+h}=Σ_m Debt_{i,m}*(Coupon_{i,m}+ResetBeta_{i,m}*ΔRate_t); ΔAFFO_i≈-ΔCashInterest_i+RentPassThrough_i`, create deterministic fixtures and implement `Market REIT index duration and price-to-NAV score`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Disclosure-derived maturity-wall factor with event-based hedged return regressions`, holdout on available historical timestamps and record AFFO forecast error, sector-neutral return IC, liquidity-adjusted drawdown, event placebo; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Japanese disclosure translation/lease renewal timing and selective REIT survivorship.; estimate actual execution J-REIT constituent liquidity, FX hedge and foreign-investor restrictions limit realized capacity., then decide No incremental post-rate-shift forecast after issuer fixed-effects and NAV-duration controls..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $85k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
