# ROADMAP — EU ETS Auction Supply Revision and Carbon Futures Carry
**Phase 0: source and math validation (weeks 1–2).** Confirm EU carbon allowances (EUA), European power utilities, allowable decision Hedge EUA futures calendar spreads against only announced changes in auction volume and verified-emissions obligations., units in `Spread_{m,n,t}=theta*(ExpectedAuctionSupply_t - ExpectedComplianceDemand_t)+beta*EnergyControls_t+epsilon_t`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed EU ETS auction calendar publication × allowance futures tenor × exchange quote timestamp fixture, deterministic Calendar-month fixed seasonal allowance spread and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Event study of auction schedule revisions and futures risk factors versus holdout baseline; optionally prototype Partial equilibrium allowance banking model with endogenous industrial abatement and policy scenarios. **Gate:** No out-of-sample spread forecast or hedge benefit net of spreads after matched energy factors.

**Phase 3: robustness (weeks 9–12).** Stress Policy revision expectations may be priced before official publication; futures/Registry coverage not contemporaneous.; evaluate EUA spread basis MAE, hedged risk reduction, net carry after fees, low-liquidity scenario loss, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
