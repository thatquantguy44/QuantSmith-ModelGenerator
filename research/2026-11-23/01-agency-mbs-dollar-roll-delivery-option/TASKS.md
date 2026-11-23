# TASKS — Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option
**All tasks: NOT STARTED.** Synthetic requirements can be developed without permissioned data.

| Task | Dependencies | Traceability | Definition of done |
|---|---|---|---|
| T-01 Audit sources, market access and legal eligibility | none | REQ-001,NFR-002 | Written rights/availability status and exception log |
| T-02 Implement public-time schema and synthetic edge cases | T-01 | REQ-001,NFR-001,AC-001 | `available_at` joins reject lookahead and bad unit |
| T-03 Build cost-inclusive `Dollar-roll implied financing vs same-tenor generic repo without delivery-option valuation` | T-02 | REQ-002,AC-002 | Exact invariant tests and worst-case costs |
| T-04 Prototype `Constrained pool-delivery optimizer with observable pool financing carry and roll prices` | T-03 | REQ-003,AC-003 | Fixed seed, model card and reproducible run |
| T-05 Conditional model expansion: Stochastic pool quality and delivery-selection real-options game with cheapest-deliverable simulation | T-04 | REQ-003 | Predeclared paired ablation; no unnecessary complexity |
| T-06 Falsify: No stable out-of-sample cost-adjusted advantage over delivery-aware manual baseline at realistic pool eligibility. | T-04 | REQ-004,AC-004 | Held-out net metrics `Net financing bps, cheapest-deliverable premium, pre-settlement fail exposure, netted capital and tail regret` including uncertainty |
| T-07 Human data/risk review and shadow-mode gate | T-06 | NFR-002,AC-005 | Signoff or explicit stop; no live execution |

## Targeted negative tests
- Future publication used before decision timestamp (reject).
- Pool price selection, payup optionality, actual pool availability and post-trade EPN leakage. (stress and explicit negative control).
- Missing/contradictory legal eligibility (abort, no optimistic default).
- No-action benchmark for unavailable executable market access.

**No tests above were run in this documentation PR.**
