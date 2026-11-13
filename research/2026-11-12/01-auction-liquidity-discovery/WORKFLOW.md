# WORKFLOW — Auction-Based Securities Lending Liquidity Discovery
```mermaid
flowchart LR
 A[Hypothesis] --> B[Data rights]
 B --> C[Point-in-time fixtures]
 C --> D[Costed baseline]
 D --> E[censored structural demand + constrained auction]
 E --> F[Paired holdout]
 F --> G{Pass falsification?}
 G -->|No| H[Negative finding]
 G -->|Yes| I[Human-reviewed shadow mode]
```
1. Define decision: set fee and allocation for scarce lendable securities.
2. Ingest only authorized inputs: Timestamped locate quotes, revisions, rejects, fills, quantities and source-specific inventory.
3. Reject future information, unsupported eligible states and unpriced cost drivers.
4. Evaluate baseline highest-fee-first feasible allocation; then candidate censored structural demand + constrained auction.
5. Report net revenue, allocative efficiency, fill rate, churn and regret, sensitivities and risk censored demand, endogenous quote selection.
6. Archive source/version/hash details, failures and signoffs.
No step is a claim of actual execution.
