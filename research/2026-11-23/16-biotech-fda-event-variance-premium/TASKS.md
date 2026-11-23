# TASKS — Biotech FDA Catalyst Probability versus Options Event Premium
**All tasks: NOT STARTED.** Synthetic requirements can be developed without permissioned data.

| Task | Dependencies | Traceability | Definition of done |
|---|---|---|---|
| T-01 Audit sources, market access and legal eligibility | none | REQ-001,NFR-002 | Written rights/availability status and exception log |
| T-02 Implement public-time schema and synthetic edge cases | T-01 | REQ-001,NFR-001,AC-001 | `available_at` joins reject lookahead and bad unit |
| T-03 Build cost-inclusive `Historical absolute event returns grouped by market cap and indication` | T-02 | REQ-002,AC-002 | Exact invariant tests and worst-case costs |
| T-04 Prototype `Regulatory-document event taxonomy + shrinkage conditional jump model` | T-03 | REQ-003,AC-003 | Fixed seed, model card and reproducible run |
| T-05 Conditional model expansion: Hierarchical Bayesian decision-state model and option-neutral density decomposition | T-04 | REQ-003 | Predeclared paired ablation; no unnecessary complexity |
| T-06 Falsify: Conditional probability model fails event-matched calibration or net executable option premium. | T-04 | REQ-004,AC-004 | Held-out net metrics `Jump variance calibration, option VRP after costs, event coverage, tail hedge error` including uncertainty |
| T-07 Human data/risk review and shadow-mode gate | T-06 | NFR-002,AC-005 | Signoff or explicit stop; no live execution |

## Targeted negative tests
- Future publication used before decision timestamp (reject).
- FDA database daily updates can lag original approval; sample selection, delistings and halted option quotes. (stress and explicit negative control).
- Missing/contradictory legal eligibility (abort, no optimistic default).
- No-action benchmark for unavailable executable market access.

**No tests above were run in this documentation PR.**
