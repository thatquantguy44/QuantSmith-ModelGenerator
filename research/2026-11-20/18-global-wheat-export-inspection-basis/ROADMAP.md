# ROADMAP — Wheat Export Inspection Revisions to Global Basis and Calendar Spreads
**Phase 0: source and math validation (weeks 1–2).** Confirm US, Black Sea and international wheat futures/physical flows, allowable decision Hedge wheat calendar spreads around official export inspection versus world balance-sheet information releases., units in `BasisChange_{r,t+h}=alpha+beta*(InspectionsPublished_t-ExpectedInspections_t)+gamma*Weather_t+epsilon`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed weekly USDA inspection release × grain class × destination × exchange quote timestamp fixture, deterministic Monthly seasonal wheat spread regression using last known WASDE and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Mixed-frequency distributed-lag export surprise model versus holdout baseline; optionally prototype Structural Bayesian crop-flow network with regional stock constraints and censoring. **Gate:** No predictive improvement after weather, futures calendar effects and contemporaneous official release lags.

**Phase 3: robustness (weeks 9–12).** Stress Weekly inspections differ from actual export commitments; Black Sea supply and policy announcements may dominate.; evaluate spread forecast delta, regional basis tracking, net slippage-adjusted hedge P&L, regime robustness, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
