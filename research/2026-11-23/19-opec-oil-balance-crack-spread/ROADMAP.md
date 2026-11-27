# ROADMAP — OPEC Oil Balance Residuals and Refined Crack-Spread Transmission
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check JODI-Oil World Database Downloads, US EIA Public API versus exact needed fields: JODI monthly crude stocks/flows, OPEC reports, EIA refinery/product balances, crack-futures settlements. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `Residual_{c,m}=Production+Imports-Exports-RefineryIntake-ΔStocks-OtherUse; Crack_t=P_product_t-ConversionRatio*P_crude_t`, create deterministic fixtures and implement `Seasonal EIA weekly inventories and oil curve`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Constrained oil balance reconciliation and local-projection crack spread model`, holdout on available historical timestamps and record Out-of-sample crack variance forecast, economic hedge cost, stock-balance residual stability; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Monthly country submission corrections, unit conversion mismatches and sanctioned flow missingness.; estimate actual execution Use executable refined product futures, contract rolls, inventory and liquidity spreads; no inference from paper spreads., then decide Residual predictive content disappears after vintages, shipping lags and front-month liquidity adjustment..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $115k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
