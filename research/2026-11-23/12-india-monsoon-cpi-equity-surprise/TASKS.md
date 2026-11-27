# TASKS — India Monsoon Surprise to Food CPI and Local Equity Pricing
**All tasks: NOT STARTED.** Synthetic requirements can be developed without permissioned data.

| Task | Dependencies | Traceability | Definition of done |
|---|---|---|---|
| T-01 Audit sources, market access and legal eligibility | none | REQ-001,NFR-002 | Written rights/availability status and exception log |
| T-02 Implement public-time schema and synthetic edge cases | T-01 | REQ-001,NFR-001,AC-001 | `available_at` joins reject lookahead and bad unit |
| T-03 Build cost-inclusive `All-India seasonal rainfall deviation plus autoregressive food CPI` | T-02 | REQ-002,AC-002 | Exact invariant tests and worst-case costs |
| T-04 Prototype `Hierarchical spatial distributed-lag regression + causal crop weighting` | T-03 | REQ-003,AC-003 | Fixed seed, model card and reproducible run |
| T-05 Conditional model expansion: Weather-to-crop graph structural state-space model with uncertainty propagation | T-04 | REQ-003 | Predeclared paired ablation; no unnecessary complexity |
| T-06 Falsify: No incremental holdout inflation forecast or stock-return effect against rainfall benchmark. | T-04 | REQ-004,AC-004 | Held-out net metrics `CPI MAE, sector neutral-return IC, hit rate net costs, seasonal robustness` including uncertainty |
| T-07 Human data/risk review and shadow-mode gate | T-06 | NFR-002,AC-005 | Signoff or explicit stop; no live execution |

## Targeted negative tests
- Future publication used before decision timestamp (reject).
- Historical IMD OGD resources lag, crop mix revisions, rainfall not yield and policy interventions. (stress and explicit negative control).
- Missing/contradictory legal eligibility (abort, no optimistic default).
- No-action benchmark for unavailable executable market access.

**No tests above were run in this documentation PR.**
