# WORKFLOW — Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes
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

1. **Domain:** EUR, CHF, JPY and USD cash-collateralized securities lending; decision: Price and hedge rebate-floor optionality embedded in cash-collateral loan agreements..
2. **Source and licensing:** FRED Data Portal, Bank of Japan Time-Series Data Search, BIS Basel III Monitoring Release, Sep 23 2026 are public starting points; OIS curves and vol surfaces with redistribution rights is gated until entitlement.
3. **Temporal contract:** Valuation at contract initiation using curve observed by quote cut-off, not future realized policy rates.
4. **Baseline:** Static contractual rebate minus benchmark with no optionality with full operational cost and feasible eligibility.
5. **Model:** Rate-tree floor valuation and curve calibration with contract clause parser, then justify any additional complexity in Multi-currency short-rate stochastic volatility and correlated collateral run-off scenario valuation.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress Floor rights and term structures vary by legal agreement; historic negative-rate regimes have sample limitations..
7. **Outcome:** Pricing replication error, stress carry, calibration error and limit-breach count. Stop if Valuation adds no meaningful incremental pricing accuracy to conservative quoted-fee schedules..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
