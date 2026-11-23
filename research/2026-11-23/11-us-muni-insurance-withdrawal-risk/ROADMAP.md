# ROADMAP — US Municipal Credit Vulnerability to Local Insurance Withdrawal
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check FEMA National Risk Index public catalog, MSRB EMMA Continuing Disclosures versus exact needed fields: County FEMA risk, EMMA issuer disclosures, municipal price quotes, property valuations, insurer exit/public rate filings. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `ΔCreditSpread_{c,t+h}=β*(Hazard_c×InsuranceShock_{c,t})+γ'X_{c,t}+μ_c+τ_t+ε`, create deterministic fixtures and implement `Debt-to-revenue and issuer-rating-only spread screen`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Geospatial panel DiD with insurance availability shock and issuer boundary crosswalk`, holdout on available historical timestamps and record Out-of-sample spread rank IC, change in tax revenue, false alerts, distress recall; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test FEMA risk baseline old; climate model not equivalent to observed insurance withdrawal; selective municipal disclosure.; estimate actual execution Muni bonds illiquid, spread carry/horizon may exceed signal; favor risk-monitoring before trading., then decide No incremental out-of-time predictive effect after socioeconomic covariates and issuer-selection controls..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $100k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
