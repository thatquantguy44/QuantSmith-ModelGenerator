# ROADMAP — CCP Default-Fund Mutualization Marginal Risk Budget
**Phase 0: source and math validation (weeks 1–2).** Confirm US/EU Treasury and derivatives clearing memberships, allowable decision Set internal clearing exposure budgets based on potential default-fund replenishment and contingent mutualized-loss allocation., units in `RiskCharge_j=ES_alpha(sum_s MutualizedLoss_{j,s} + Replenishment_{j,s})`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed CCP membership × cleared product × default stress scenario fixture, deterministic Exposure limit proportional to initial margin only and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Transparent worst-two-member default waterfall simulator versus holdout baseline; optionally prototype Coherent-risk allocation via Shapley/gradient ES under correlated default network scenarios. **Gate:** No material differentiation in conditional tail loss versus margin-only limits after conservative parameter uncertainty.

**Phase 3: robustness (weeks 9–12).** Stress Actual default fund contributions and replenishment terms may differ from public examples and vary by venue.; evaluate tail capital charge, stress shortfall, liquidity buffer usage, net clearing benefit, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
