# ROADMAP — SFTR Reporting Regime Drift and Public-Private Divergence Detector
**Phase 0: source and math validation (weeks 1–2).** Confirm European securities financing transaction repositories, allowable decision Detect structural reporting-quality breaks before using reported SFTR aggregates as market exposure signals., units in `Alarm_t=1{PosteriorP(change|feature_history)>q}; minimize detection_delay+lambda*false_alarms`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed SFTR public aggregate series × jurisdiction × report vintage fixture, deterministic Fixed ±3-sigma z-score alert on each series and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Robust multivariate Bayesian online change-point detection versus holdout baseline; optionally prototype Hierarchical regime/missingness change-point models with document version embeddings as covariates. **Gate:** Synthetic change fixtures not detected within agreed delay or false alerts exceed preregistered burden.

**Phase 3: robustness (weeks 9–12).** Stress Only public aggregate data may be available, making root-cause verification incomplete.; evaluate break detection delay, false alarms, post-correction economic interpretation stability, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
