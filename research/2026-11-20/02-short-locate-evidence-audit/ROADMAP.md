# ROADMAP — Reg SHO Locate Evidence and Borrow-Capacity Audit Engine
**Phase 0: source and math validation (weeks 1–2).** Confirm US equity securities lending and short-sale compliance, allowable decision Block or escalate a short-sale request if contemporaneous legally qualifying locate evidence or remaining documented quantity is insufficient., units in `min_policy c_FN*FN + c_FP*FP + c_D*Delay subject to permitted(request,t)<=documented_available_qty(t)`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed short-sale request × account × security × source × event timestamp fixture, deterministic End-of-day deterministic locate exception SQL rules and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Typed event-sourcing finite-state verification with causal explainability versus holdout baseline; optionally prototype Conformal anomaly scoring for ambiguous evidence routed to human review, never autonomous compliance override. **Gate:** Fails to flag intentionally missing/expired/overused locates on synthetic fixtures or blocks materially more valid trades than comparator.

**Phase 3: robustness (weeks 9–12).** Stress Reg SHO exemptions, broker responsibilities and settlement rules require qualified legal interpretation.; evaluate prevented invalid requests, false blocks, recall error, audit completion time, p99 latency, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
