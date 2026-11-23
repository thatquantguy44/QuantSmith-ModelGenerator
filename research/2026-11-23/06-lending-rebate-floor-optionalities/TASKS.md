# TASKS — Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes
**All tasks: NOT STARTED.** Synthetic requirements can be developed without permissioned data.

| Task | Dependencies | Traceability | Definition of done |
|---|---|---|---|
| T-01 Audit sources, market access and legal eligibility | none | REQ-001,NFR-002 | Written rights/availability status and exception log |
| T-02 Implement public-time schema and synthetic edge cases | T-01 | REQ-001,NFR-001,AC-001 | `available_at` joins reject lookahead and bad unit |
| T-03 Build cost-inclusive `Static contractual rebate minus benchmark with no optionality` | T-02 | REQ-002,AC-002 | Exact invariant tests and worst-case costs |
| T-04 Prototype `Rate-tree floor valuation and curve calibration with contract clause parser` | T-03 | REQ-003,AC-003 | Fixed seed, model card and reproducible run |
| T-05 Conditional model expansion: Multi-currency short-rate stochastic volatility and correlated collateral run-off scenario valuation | T-04 | REQ-003 | Predeclared paired ablation; no unnecessary complexity |
| T-06 Falsify: Valuation adds no meaningful incremental pricing accuracy to conservative quoted-fee schedules. | T-04 | REQ-004,AC-004 | Held-out net metrics `Pricing replication error, stress carry, calibration error and limit-breach count` including uncertainty |
| T-07 Human data/risk review and shadow-mode gate | T-06 | NFR-002,AC-005 | Signoff or explicit stop; no live execution |

## Targeted negative tests
- Future publication used before decision timestamp (reject).
- Floor rights and term structures vary by legal agreement; historic negative-rate regimes have sample limitations. (stress and explicit negative control).
- Missing/contradictory legal eligibility (abort, no optimistic default).
- No-action benchmark for unavailable executable market access.

**No tests above were run in this documentation PR.**
