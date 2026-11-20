# ROADMAP — Evergreen Repo Early-Termination Optionality Risk Budget
**Phase 0: source and math validation (weeks 1–2).** Confirm Open and evergreen secured funding agreements, allowable decision Set rate/tenor risk charges for unilateral termination and extension rights in open repo or evergreen funding., units in `V_t=max(ExerciseValue_t, Carry_t+discount*E_t[V_{t+1}]) subject to NoticeDays,Eligibility`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed contract × notice period × funding day × interest-rate state fixture, deterministic Static repo spread plus deterministic notice-day funding reserve and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Least-squares Monte Carlo for bilateral asymmetric stop decisions versus holdout baseline; optionally prototype Nonzero-sum stochastic game with liquidity-dependent termination intensities. **Gate:** Option charge unstable or no improvement over conservative notice reserve in stress holdouts.

**Phase 3: robustness (weeks 9–12).** Stress Non-observed counterparty exercise behavior; public term repo alone does not identify proprietary notice clauses.; evaluate replacement funding loss, option premium calibration, cash-flow stress, tail liquidity gap, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
