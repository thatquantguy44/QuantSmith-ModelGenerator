# TASKS — Corporate Bond Securities Lending from CDS Basis Hedge Demand
**All tasks: NOT STARTED.** Synthetic requirements can be developed without permissioned data.

| Task | Dependencies | Traceability | Definition of done |
|---|---|---|---|
| T-01 Audit sources, market access and legal eligibility | none | REQ-001,NFR-002 | Written rights/availability status and exception log |
| T-02 Implement public-time schema and synthetic edge cases | T-01 | REQ-001,NFR-001,AC-001 | `available_at` joins reject lookahead and bad unit |
| T-03 Build cost-inclusive `Trailing borrower request count and issue-size utilization` | T-02 | REQ-002,AC-002 | Exact invariant tests and worst-case costs |
| T-04 Prototype `Matched event study plus borrow-arrival hazard conditional on CDS-bond basis` | T-03 | REQ-003,AC-003 | Fixed seed, model card and reproducible run |
| T-05 Conditional model expansion: Structural joint CDS/bond market-maker inventory model with selection-corrected demand | T-04 | REQ-003 | Predeclared paired ablation; no unnecessary complexity |
| T-06 Falsify: Estimated basis effects fail paired holdouts or increase rejected locates after slippage and liquidity controls. | T-04 | REQ-004,AC-004 | Held-out net metrics `Borrow-arrival log score, realized net fee improvement, stale quote rate and borrow supply capacity` including uncertainty |
| T-07 Human data/risk review and shadow-mode gate | T-06 | NFR-002,AC-005 | Signoff or explicit stop; no live execution |

## Targeted negative tests
- Future publication used before decision timestamp (reject).
- Non-executable CDS quotes, bond TRACE delay and endogeneity of credit distress. (stress and explicit negative control).
- Missing/contradictory legal eligibility (abort, no optimistic default).
- No-action benchmark for unavailable executable market access.

**No tests above were run in this documentation PR.**
