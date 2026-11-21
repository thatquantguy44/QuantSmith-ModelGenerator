# ROADMAP — Canadian Mortgage Renewal Cohorts to Bank Credit-Risk Dispersion
**Phase 0: source and math validation (weeks 1–2).** Confirm Canadian banks, mortgage credit and bank equity/CDS, allowable decision Hedge Canadian bank credit/equity risk using public maturity-cohort mortgage renewal exposure rather than broad unemployment alone., units in `Shock_{cohort,t}=Balance_{cohort}*max(RenewalPayment_t-OldPayment,0); ECL_{bank,t+h}=beta*Shock+controls`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed Canadian mortgage cohort × monthly public release × bank quarterly filing fixture, deterministic Bank loss sensitivity to national unemployment and policy rate alone and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Vintage-cohort mortgage reset microsimulation from public aggregates versus holdout baseline; optionally prototype Hierarchical hazard model linking repricing, prepayment and issuer loan-level exposures. **Gate:** No cross-bank predictive signal after public loan books and unemployment/rate controls, or estimates too wide to act on.

**Phase 3: robustness (weeks 9–12).** Stress Public aggregate cohorts do not identify each bank's borrower vintage distribution or underwriting quality.; evaluate future loss forecast gain, bank-spread risk hedging, sensitivity to vintage assumptions, net hedging cost, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
