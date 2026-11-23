# ROADMAP — Borrow Scarcity Causal Effect on Equity Market-Maker Quoted Depth
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check SEC EDGAR Data Access versus exact needed fields: Borrow availability and fees, market quotes/trades, issuer event calendars and exclusion instruments. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `Depth_{i,t}=α_i+δ_t+β*BorrowSupplyShock_{i,t}+γ'X_{i,t}+ε_{i,t}; H0: β=0`, create deterministic fixtures and implement `Spread/depth forecasting using only realized volatility and market cap`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Matched differences-in-differences/event-time instrumental analysis`, holdout on available historical timestamps and record Event-time β confidence interval, placebos, effective spread, depth and incremental risk price; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Selection on distressed shorts, simultaneous volatility and hard-to-borrow endogenous events.; estimate actual execution Not an unconditional trading signal; capacity depends on quote depth and borrow clearance, include adverse selection., then decide No pre-registered effect with valid pretrends/instruments or effect only on illiquid untradeable names..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $120k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
