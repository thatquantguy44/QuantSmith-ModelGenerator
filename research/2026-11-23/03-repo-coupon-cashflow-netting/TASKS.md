# TASKS — Repo Coupon and Principal Event Cash-Flow Netting Scheduler
**All tasks: NOT STARTED.** Synthetic requirements can be developed without permissioned data.

| Task | Dependencies | Traceability | Definition of done |
|---|---|---|---|
| T-01 Audit sources, market access and legal eligibility | none | REQ-001,NFR-002 | Written rights/availability status and exception log |
| T-02 Implement public-time schema and synthetic edge cases | T-01 | REQ-001,NFR-001,AC-001 | `available_at` joins reject lookahead and bad unit |
| T-03 Build cost-inclusive `Gross independent payment processing with static buffer` | T-02 | REQ-002,AC-002 | Exact invariant tests and worst-case costs |
| T-04 Prototype `Mixed-integer liquidity scheduling with eligibility/netting-set constraints` | T-03 | REQ-003,AC-003 | Fixed seed, model card and reproducible run |
| T-05 Conditional model expansion: Stochastic event-flow MPC with missed payment penalties and legal-entity netting restrictions | T-04 | REQ-003 | Predeclared paired ablation; no unnecessary complexity |
| T-06 Falsify: No capacity-adjusted cost reduction versus pre-netted conventional operations or violations of payment rights. | T-04 | REQ-004,AC-004 | Held-out net metrics `Peak cash buffer, gross payment count, exception cost, settlement timeliness` including uncertainty |
| T-07 Human data/risk review and shadow-mode gate | T-06 | NFR-002,AC-005 | Signoff or explicit stop; no live execution |

## Targeted negative tests
- Future publication used before decision timestamp (reject).
- Wrong beneficial-ownership treatment, netting rights and special cash settlement terms. (stress and explicit negative control).
- Missing/contradictory legal eligibility (abort, no optimistic default).
- No-action benchmark for unavailable executable market access.

**No tests above were run in this documentation PR.**
