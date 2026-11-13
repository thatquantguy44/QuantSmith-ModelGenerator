# TASKS — Cross-Book Securities Finance Identity Reconciliation Graph
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to Synthetic records containing lifecycle events, ISIN/CUSIP, product type, settlement date, amount, counterparty alias and amendment chain. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `securities-finance-identity-reconciler` schema and synthetic fixtures at source record × canonical candidate × event version × timestamp | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Exact ID join plus manually triaged fuzzy-name matches. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Bipartite deterministic matching with hard identity constraints and provenance. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Human-review active-learning on uncertain clusters with error budget and privacy-preserving synthetic tests. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate false merge rate, unmatched %, time to resolve, duplicate exposure USD, manual review hours.; stress LLM or probabilistic model can silently merge legally distinct entities or settlement legs. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_securities_finance_identity_reconciler_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_securities_finance_identity_reconciler_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_securities_finance_identity_reconciler_paired`: split embargo and matched action support.
- AC-004 → `test_securities_finance_identity_reconciler_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_securities_finance_identity_reconciler_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
