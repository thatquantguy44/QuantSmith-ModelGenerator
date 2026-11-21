# ROADMAP — US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface
**Phase 0: source and math validation (weeks 1–2).** Confirm US TIPS, nominal Treasuries, inflation swaps, allowable decision Select TIPS versus nominal duration-hedged exposure around CPI index-ratio carry windows., units in `TIPSReturn_t=RealYieldReturn_t+KnownIndexAccrual_t+InflationNews_t+LiquidityResidual_t`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed TIPS CUSIP × CPI/index-ratio effective date × decision timestamp fixture, deterministic Duration-matched TIPS-minus-nominal bond without CPI-calendar signal and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Deterministic index-ratio accrual and liquidity-factor attribution versus holdout baseline; optionally prototype State-space real/nominal curve with stochastic CPI surprise and inflation floor convexity. **Gate:** Improvement vanishes versus a carry-only and time-matched duration hedge after execution spread costs.

**Phase 3: robustness (weeks 9–12).** Stress Illiquid issue quotations, inflation floor optionality, unrevised CPI data and seasonality overfit.; evaluate hedge tracking error, information ratio net of costs, index replication error, carry decomposition residual, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
