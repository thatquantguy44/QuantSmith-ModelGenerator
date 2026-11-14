# TASKS — Tri-Party Collateral Eligibility Clause-to-Constraint Compiler
**Status:** All tasks TODO. Proposed test names are NOT run or present in code.

| ID | Task | Requirements | Concrete definition of done |
|---|---|---|---|
| T-001 | Verify market/legal permissions and rights to Synthetic collateral schedules; asset master; rating/issuer; eligibility categories; haircut tables; human-labeled clause examples. | REQ-001,NFR-002 | Signed accessible-source and action/market eligibility matrix |
| T-002 | Build immutable `triparty-eligibility-compiler` schema and synthetic fixtures at contract clause × effective version × collateral asset × valuation time | REQ-001,NFR-001,AC-001 | Future-vintage, duplicates and revisions rejected deterministically |
| T-003 | Implement Rule tables hand-transcribed and checked by two human operators. with realistic frictions | REQ-002,AC-002 | Math, units, feasibility and no-trade unit tests green |
| T-004 | Implement initial Schema-constrained text extraction with symbolic eligibility evaluation and abstention. | REQ-003,AC-003 | Pinned config, deterministic training, reproducible candidate outputs |
| T-005 | Design Contradiction-aware graph of rule amendments with formal test generation and reviewer feedback. ablation only if needed | REQ-003 | Incremental complexity budget versus simple candidate recorded |
| T-006 | Freeze chronological holdout and matched economic replay | REQ-004,NFR-001,AC-003 | Same action set; no post-decision information; execution cost included |
| T-007 | Evaluate false eligibility acceptance rate, false rejection rate, review labor, coverage, abstention, parse latency.; stress Natural-language ambiguity, contract precedence and jurisdiction-specific clauses make full automation unsafe. | REQ-004,AC-004 | CI/stress metrics and fail/abstention report generated |
| T-008 | Review legal/data boundaries, stop/go and shadow plan | NFR-002,AC-005 | Explicit independent reviewer sign-off; no automatic deployment |

## Acceptance-test mapping (planned)
- AC-001 → `test_triparty_eligibility_compiler_asof`: sources unavailable at decision time must throw a typed error.
- AC-002 → `test_triparty_eligibility_compiler_baseline`: compare with hand-calculated synthetic examples.
- AC-003 → `test_triparty_eligibility_compiler_paired`: split embargo and matched action support.
- AC-004 → `test_triparty_eligibility_compiler_risk`: bounds, stress and cost sensitivity.
- AC-005 → `test_triparty_eligibility_compiler_public_gate`: confidential and unauthorized record rejection.

## Completion caveat
Only design documents exist. No test has been implemented or passed; DO NOT mark anything DONE until a verified run report and owner approval exists.
