# WORKFLOW — OPEC Oil Balance Residuals and Refined Crack-Spread Transmission
```mermaid
flowchart LR
 A[Scoped question] --> B[Legal source gate]
 B --> C[As-of publication ledger]
 C --> D[Deterministic baseline]
 D --> E[Candidate model]
 E --> F[Held-out costed replay]
 F --> G{Falsification}
 G -->|Reject| H[Negative result archived]
 G -->|Pass| I[Independent human review]
```

1. **Domain:** OPEC producers, global crude and Atlantic Basin refined products; decision: Hedge product crack spreads when public crude production and stock-flow residuals imply inventory stress..
2. **Source and licensing:** JODI-Oil World Database Downloads, US EIA Public API are public starting points; ICE/NYMEX refined product and crude futures settlement histories is gated until entitlement.
3. **Temporal contract:** JODI typically publishes next-month and revises; align release date, not reporting month; execute only after release.
4. **Baseline:** Seasonal EIA weekly inventories and oil curve with full operational cost and feasible eligibility.
5. **Model:** Constrained oil balance reconciliation and local-projection crack spread model, then justify any additional complexity in Multi-region Bayesian trade flow accounting with measurement error and shipping lags.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress Monthly country submission corrections, unit conversion mismatches and sanctioned flow missingness..
7. **Outcome:** Out-of-sample crack variance forecast, economic hedge cost, stock-balance residual stability. Stop if Residual predictive content disappears after vintages, shipping lags and front-month liquidity adjustment..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
