# ROADMAP — Noncash Collateral Correlation-Cluster Haircut Controller
**Phase 0: source and math validation (weeks 1–2).** Confirm Multi-asset collateral supporting US/EU securities loans, allowable decision Recommend minimum defensive haircuts for a collateral basket based on joint concentration and liquidation correlation., units in `min_h CarryCost(h) subject to P(Loss(Collateral,Loan,h)>Limit)<=alpha and issuer_weight<=cap`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed collateral security × issuer cluster × loan exposure × as-of time fixture, deterministic Uniform issuer/asset-class static haircut and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Scenario CVaR optimization with issuer cluster caps versus holdout baseline; optionally prototype Distributionally robust ambiguity-set CVaR with wrong-way liquidity correlation. **Gate:** Risk benefit disappears when using stressed-correlation holdouts or violates legal haircut floors.

**Phase 3: robustness (weeks 9–12).** Stress Asset covariance may break exactly when haircuts are needed and public free-float proxies omit liquidation controls.; evaluate shortfall ES, collateral usage, haircut turnover, stress exceptions, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
