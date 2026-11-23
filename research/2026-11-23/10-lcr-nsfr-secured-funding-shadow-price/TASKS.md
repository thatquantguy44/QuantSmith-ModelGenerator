# TASKS — Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral
**All tasks: NOT STARTED.** Synthetic requirements can be developed without permissioned data.

| Task | Dependencies | Traceability | Definition of done |
|---|---|---|---|
| T-01 Audit sources, market access and legal eligibility | none | REQ-001,NFR-002 | Written rights/availability status and exception log |
| T-02 Implement public-time schema and synthetic edge cases | T-01 | REQ-001,NFR-001,AC-001 | `available_at` joins reject lookahead and bad unit |
| T-03 Build cost-inclusive `Rank repo offers by quoted rate subject to gross notional limits` | T-02 | REQ-002,AC-002 | Exact invariant tests and worst-case costs |
| T-04 Prototype `Linear/mixed-integer secured funding allocation with LCR/NSFR dual-price attribution` | T-03 | REQ-003,AC-003 | Fixed seed, model card and reproducible run |
| T-05 Conditional model expansion: Scenario-based shadow-price frontier with intraday and quarter-end liquidity risk | T-04 | REQ-003 | Predeclared paired ablation; no unnecessary complexity |
| T-06 Falsify: No cost difference over conservative liquidity-constrained benchmark or unstable/uninterpretable duals. | T-04 | REQ-004,AC-004 | Held-out net metrics `All-in liquidity-adjusted cost, marginal dual price, buffer breaches, sensitivity to rule version` including uncertainty |
| T-07 Human data/risk review and shadow-mode gate | T-06 | NFR-002,AC-005 | Signoff or explicit stop; no live execution |

## Targeted negative tests
- Future publication used before decision timestamp (reject).
- Entity-specific regulatory implementation and internal forecasts differ; cannot reconstruct actual LCR from public totals. (stress and explicit negative control).
- Missing/contradictory legal eligibility (abort, no optimistic default).
- No-action benchmark for unavailable executable market access.

**No tests above were run in this documentation PR.**
