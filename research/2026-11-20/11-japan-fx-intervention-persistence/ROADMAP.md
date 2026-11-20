# ROADMAP — Japan FX Intervention Impact and Option-Skew Persistence
**Phase 0: source and math validation (weeks 1–2).** Confirm Japan USD/JPY, yen crosses and FX options, allowable decision Determine when to reduce/hedge yen exposure following **publicly observed** intervention or subsequent official disclosure., units in `DeltaSkew_{t,h}=beta*InterventionKnownAt_t+gamma*MacroControls_t+epsilon_{t,h}`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed intervention disclosure event × FX option tenor × quote timestamp fixture, deterministic Standard spot momentum and monetary-policy announcement dummy and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Disclosure-timestamp event study with matched controls and local projections versus holdout baseline; optionally prototype Partial-identification causal synthetic control separating information, execution and portfolio-flow channels. **Gate:** No differential response versus rate/central-bank news controls on withheld intervention disclosures or net-option-cost results.

**Phase 3: robustness (weeks 9–12).** Stress Actual intervention execution is not transparently known in real time; small event count undermines causal certainty.; evaluate incremental forward skew/vol forecast skill, delta-hedged net P&L, placebo events, risk-adjusted drawdown, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
