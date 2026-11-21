# ROADMAP — Korean Household Debt-Service Shock to Bank–Consumer Equity Spread
**Phase 0: source and math validation (weeks 1–2).** Confirm South Korea household credit, KOSPI/KOSDAQ banks and consumer discretionary, allowable decision Hedge relative exposure of Korean bank and consumer equities across household debt-service regime changes., units in `RelativeEPS_{b,c,t+h}=a+beta*DSRSurprise_t+gamma*PolicyRate_t+delta*FX_t+epsilon`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed quarterly DSR release × issuer × accounting period × price timestamp fixture, deterministic Equal-beta long banks short consumer discretionary with lagged policy-rate signal and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Panel local projections with shrinkage and sector time fixed effects versus holdout baseline; optionally prototype Dynamic heterogeneous household credit impulse response with instrumented policy-rate shocks. **Gate:** No stable expected-earnings or beta-neutral sector difference once rates and economy factors are controlled.

**Phase 3: robustness (weeks 9–12).** Stress Endogenous rate policy and sector composition cause confounding; public issuer histories need delisting continuity.; evaluate cross-sector earnings forecast delta, beta-neutral IR, worst-regime drawdown, capacity after local spreads, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
