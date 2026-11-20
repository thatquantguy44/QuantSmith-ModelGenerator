# ROADMAP — European CSDR Penalty-Aware Settlement Queue Prioritization
**Phase 0: source and math validation (weeks 1–2).** Confirm EU CSD securities settlement / securities finance return legs, allowable decision Prioritize settlement instructions under explicit penalty eligibility and scarce processing resources., units in `min_pi E[sum_i penalty_i*1(fail_i at close)+delay_cost_i] subject to legal_priority_i and capacity_t`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed instruction × CSD × ISIN × intended settlement day × decision time fixture, deterministic FIFO or largest-notional-first allowed settlement priority and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Constrained weighted-shortest-processing-time queue policy with eligibility rules versus holdout baseline; optionally prototype Approximate dynamic programming under stochastic matched delivery arrival times. **Gate:** No statistically measurable improvement in held-out synthetic and later approved settlement scenarios under equal capacity.

**Phase 3: robustness (weeks 9–12).** Stress Misclassification of non-attributable fail causes or legal exclusion yields incorrect optimized queues.; evaluate penalty liability, fail-days, priority-rule violations, operational throughput, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
