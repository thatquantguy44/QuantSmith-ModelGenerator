# TASKS — Sovereign DSA Rating Migration Event Pricing for Frontier Bonds
**All tasks: NOT STARTED.** Synthetic requirements can be developed without permissioned data.

| Task | Dependencies | Traceability | Definition of done |
|---|---|---|---|
| T-01 Audit sources, market access and legal eligibility | none | REQ-001,NFR-002 | Written rights/availability status and exception log |
| T-02 Implement public-time schema and synthetic edge cases | T-01 | REQ-001,NFR-001,AC-001 | `available_at` joins reject lookahead and bad unit |
| T-03 Build cost-inclusive `Latest public debt-to-GDP and reserves ratio` | T-02 | REQ-002,AC-002 | Exact invariant tests and worst-case costs |
| T-04 Prototype `Multi-state ordinal risk migration model with publication-aligned survival validation` | T-03 | REQ-003,AC-003 | Fixed seed, model card and reproducible run |
| T-05 Conditional model expansion: Bayesian sovereign hazard with IMF policy intervention and restructuring recovery scenarios | T-04 | REQ-003 | Predeclared paired ablation; no unnecessary complexity |
| T-06 Falsify: No improvement over conservative sovereign ratings baseline, or price move entirely before public timestamp. | T-04 | REQ-004,AC-004 | Held-out net metrics `Default Brier score, out-of-time risk precision, spread change, no-trade capacity flags` including uncertainty |
| T-07 Human data/risk review and shadow-mode gate | T-06 | NFR-002,AC-005 | Signoff or explicit stop; no live execution |

## Targeted negative tests
- Future publication used before decision timestamp (reject).
- DSA coverage selection and program endogeneity, non-tradable distressed bonds, rare default events. (stress and explicit negative control).
- Missing/contradictory legal eligibility (abort, no optimistic default).
- No-action benchmark for unavailable executable market access.

**No tests above were run in this documentation PR.**
