# ROADMAP — Asia–US Cross-Listed ADR Opening Auction Information Transfer
**Phase 0: source and math validation (weeks 1–2).** Confirm US ADRs and Korea/Japan/Taiwan/Hong Kong local shares, allowable decision Choose hedge and execution timing for US ADR versus home-market overnight fair value., units in `FairADR_{i,t}=Ratio_i*LocalPrice_{i,homeclose}*FX_{i,t}+CrossMarketNews_{i,t}`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed ADR × home-market session × US opening-auction timestamp fixture, deterministic Last home close × publicly known ADR conversion ratio × contemporaneous FX spot and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare State-space asynchronous Kalman fair-value update using futures and related peer prices versus holdout baseline; optionally prototype Continuous-time latent-price discovery with joint jump and optimal execution inventory control. **Gate:** No consistent opening execution improvement after financing, foreign exchange, depositary and auction spread costs.

**Phase 3: robustness (weeks 9–12).** Stress ADR conversion fees, access restrictions, local holidays and stale home quotes create phantom arbitrage.; evaluate auction fair-value error, paired realized slippage, inventory risk, settlement/convertibility feasibility, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
