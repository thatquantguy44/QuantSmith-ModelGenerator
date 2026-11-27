# ROADMAP — Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check FRED Data Portal, Bank of Japan Time-Series Data Search, BIS Basel III Monitoring Release, Sep 23 2026 versus exact needed fields: Historical overnight benchmarks, collateral currency curves, cash balances, contract rebate-floor clauses. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `PV_floor=E^Q[Σ_t DF_t*CashCollateral_t*max(K-r_t,0)*Δt]; Revenue=baseFee+PV_floor-hedgeCost`, create deterministic fixtures and implement `Static contractual rebate minus benchmark with no optionality`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Rate-tree floor valuation and curve calibration with contract clause parser`, holdout on available historical timestamps and record Pricing replication error, stress carry, calibration error and limit-breach count; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Floor rights and term structures vary by legal agreement; historic negative-rate regimes have sample limitations.; estimate actual execution Profit only if floors contractually negotiated; hedge notional and floor illiquidity restrict scale., then decide Valuation adds no meaningful incremental pricing accuracy to conservative quoted-fee schedules..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $80k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
