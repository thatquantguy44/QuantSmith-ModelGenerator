# TASKS — Securities Loan Retroactive Rate Amendment Revenue Assurance
**All tasks: NOT STARTED.** Synthetic requirements can be developed without permissioned data.

| Task | Dependencies | Traceability | Definition of done |
|---|---|---|---|
| T-01 Audit sources, market access and legal eligibility | none | REQ-001,NFR-002 | Written rights/availability status and exception log |
| T-02 Implement public-time schema and synthetic edge cases | T-01 | REQ-001,NFR-001,AC-001 | `available_at` joins reject lookahead and bad unit |
| T-03 Build cost-inclusive `Latest agreed fee × end-period balance × elapsed days` | T-02 | REQ-002,AC-002 | Exact invariant tests and worst-case costs |
| T-04 Prototype `Bitemporal finite-state rate and loan lifecycle ledger with invariant checks` | T-03 | REQ-003,AC-003 | Fixed seed, model card and reproducible run |
| T-05 Conditional model expansion: Probabilistic anomaly prioritization atop an exact contract-aware billing engine | T-04 | REQ-003 | Predeclared paired ablation; no unnecessary complexity |
| T-06 Falsify: No improvement in high-severity seeded exceptions relative to deterministic ledger, or unauthorized dispute actions. | T-04 | REQ-004,AC-004 | Held-out net metrics `Synthetic exception precision/recall, manual hours, invoice basis-point leakage, false escalation rate` including uncertainty |
| T-07 Human data/risk review and shadow-mode gate | T-06 | NFR-002,AC-005 | Signoff or explicit stop; no live execution |

## Targeted negative tests
- Future publication used before decision timestamp (reject).
- Contract-level bilateral waiver rules, fee confirmation ambiguity and out-of-order event feeds. (stress and explicit negative control).
- Missing/contradictory legal eligibility (abort, no optimistic default).
- No-action benchmark for unavailable executable market access.

**No tests above were run in this documentation PR.**
