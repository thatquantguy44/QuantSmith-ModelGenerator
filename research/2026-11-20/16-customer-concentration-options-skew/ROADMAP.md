# ROADMAP — Issuer Customer-Concentration Disclosure to Earnings Options Skew
**Phase 0: source and math validation (weeks 1–2).** Confirm US listed single-name equity options and SEC 10-K/10-Q issuers, allowable decision Hedge customer-loss jump risk in companies with concentrated customers using explicitly costed options structures., units in `DownsideSkew_{i,t}=a+beta*CustomerHHI_{i,t-known}+gamma*EventControls_{i,t}+epsilon`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed issuer accepted filing × reported customer share × options quote timestamp fixture, deterministic Size/leverage/industry/earnings event-only option skew estimator and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Censored-disclosure panel with inverse observation probability adjustment versus holdout baseline; optionally prototype Jump-diffusion structural model of concentrated-customer exit hazard. **Gate:** No post-filing incremental skew or hedge gain beyond conventional earnings-related jump risk.

**Phase 3: robustness (weeks 9–12).** Stress Customer concentrations may be anonymized and nonrandomly omitted; options trade data can be illiquid.; evaluate post-filing skew residual, risk hedge efficiency, delta-neutral net performance and disclosure coverage, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
