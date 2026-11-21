# ROADMAP — Public BDC Portfolio Fair-Value Markdown Lead Indicator
**Phase 0: source and math validation (weeks 1–2).** Confirm US public BDC equities, leveraged loans and credit sentiment, allowable decision Prioritize due diligence or credit hedges where public business development company holdings imply delayed loan fair-value marks., units in `RiskScore_{loan,t}=f(PriceToCost_{t},NonAccrual_{t},Sector_{t},FundLag_{t})`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed BDC filing × portfolio company/sector × disclosure timestamp fixture, deterministic BDC aggregate NAV discount and published nonaccrual percentage and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Issuer-level mark-hazard panel with censored holdings and missing-not-at-random controls versus holdout baseline; optionally prototype Hierarchical Bayesian marked-to-market credit migration model with portfolio network dependence. **Gate:** No improvement over current NAV discount/nonaccrual baseline in later quarters or effects only known after financial reports.

**Phase 3: robustness (weeks 9–12).** Stress BDC portfolio company identities, valuation methods and distressed sales are not uniformly disclosed; matching bias.; evaluate future credit-event AUC/PR, mark-calibration error, NAV stress accuracy, opportunity capacity, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
