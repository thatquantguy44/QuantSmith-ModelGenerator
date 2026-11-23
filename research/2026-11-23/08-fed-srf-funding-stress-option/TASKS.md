# TASKS — Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal
**All tasks: NOT STARTED.** Synthetic requirements can be developed without permissioned data.

| Task | Dependencies | Traceability | Definition of done |
|---|---|---|---|
| T-01 Audit sources, market access and legal eligibility | none | REQ-001,NFR-002 | Written rights/availability status and exception log |
| T-02 Implement public-time schema and synthetic edge cases | T-01 | REQ-001,NFR-001,AC-001 | `available_at` joins reject lookahead and bad unit |
| T-03 Build cost-inclusive `SOFR-GC spread threshold with no SRF information` | T-02 | REQ-002,AC-002 | Exact invariant tests and worst-case costs |
| T-04 Prototype `Event-conditioned calibrated logistic hazard with lag-safe publication ledger` | T-03 | REQ-003,AC-003 | Fixed seed, model card and reproducible run |
| T-05 Conditional model expansion: Structural real-option exercise mapping latent facility usage and dealer cash constraints | T-04 | REQ-003 | Predeclared paired ablation; no unnecessary complexity |
| T-06 Falsify: No holdout information gain after timing correction, or false positives overwhelm funding buffer costs. | T-04 | REQ-004,AC-004 | Held-out net metrics `Brier score, AUPRC, stress false alarm, lead-time, calibrated probability` including uncertainty |
| T-07 Human data/risk review and shadow-mode gate | T-06 | NFR-002,AC-005 | Signoff or explicit stop; no live execution |

## Targeted negative tests
- Future publication used before decision timestamp (reject).
- SRF operational parameter changes, known policy regime shifts, lack of entity-level same-day data. (stress and explicit negative control).
- Missing/contradictory legal eligibility (abort, no optimistic default).
- No-action benchmark for unavailable executable market access.

**No tests above were run in this documentation PR.**
