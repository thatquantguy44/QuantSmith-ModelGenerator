# ROADMAP — ETF Creation/Redemption Basket Shock to Stock-Loan Supply
**Phase 0: source and math validation (weeks 1–2).** Confirm US equity ETFs and underlying stock loan, allowable decision Reserve lendable constituent supply ahead of known or forecasted ETF in-kind redemption/creation windows., units in `DeltaSupply_{i,t+h}=alpha_i+beta*BasketsDelta_{i,t}+gamma*Controls_{i,t}+epsilon`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed ETF × constituent × creation/redemption day × publication time fixture, deterministic Change in ETF shares outstanding plus index-event dummy and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Hierarchical event study with issuer-basket aggregation and controls versus holdout baseline; optionally prototype Instrumented flow shock model addressing ETF price-demand endogeneity. **Gate:** No incremental held-out inventory signal after availability alignment and underlying stock flow controls.

**Phase 3: robustness (weeks 9–12).** Stress Most executable AP basket details and actual stock-loan supply are not public.; evaluate inventory forecast MAE, short availability calibration, incremental net inventory carry, execution slippage, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
