# WORKFLOW — Loan Recall Early-Exercise Boundary
```mermaid
flowchart LR
 A[Hypothesis] --> B[Data rights]
 B --> C[Point-in-time fixtures]
 C --> D[Costed baseline]
 D --> E[constrained survival and stopping model]
 E --> F[Paired holdout]
 F --> G{Pass falsification?}
 G -->|No| H[Negative finding]
 G -->|Yes| I[Human-reviewed shadow mode]
```
1. Define decision: forecast compliant beneficial-owner recall exercise and source replacement.
2. Ingest only authorized inputs: Loan age, fee, recalls, corporate action calendar, owner restrictions, replacement cost.
3. Reject future information, unsupported eligible states and unpriced cost drivers.
4. Evaluate baseline constant owner-specific recall probability; then candidate constrained survival and stopping model.
5. Report recall warning, replacement cost, calibration and fail prevention, sensitivities and risk governance and fiduciary rights cannot be traded away.
6. Archive source/version/hash details, failures and signoffs.
No step is a claim of actual execution.
