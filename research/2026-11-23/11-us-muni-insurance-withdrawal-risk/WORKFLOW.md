# WORKFLOW — US Municipal Credit Vulnerability to Local Insurance Withdrawal
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

1. **Domain:** United States coastal, wildfire and flood-exposed municipal issuers; decision: Prioritize municipal-credit surveillance and pricing by property tax base sensitivity to insurance availability..
2. **Source and licensing:** FEMA National Risk Index public catalog, MSRB EMMA Continuing Disclosures are public starting points; Muni TRACE-like transaction data, catastrophe insurer premium/rate datasets is gated until entitlement.
3. **Temporal contract:** County/issuer boundary vintage and disclosure posting timestamp; FEMA risk version frozen at decision date.
4. **Baseline:** Debt-to-revenue and issuer-rating-only spread screen with full operational cost and feasible eligibility.
5. **Model:** Geospatial panel DiD with insurance availability shock and issuer boundary crosswalk, then justify any additional complexity in Graph exposure propagation into municipal tax receipts with heterogeneous hazard risk.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress FEMA risk baseline old; climate model not equivalent to observed insurance withdrawal; selective municipal disclosure..
7. **Outcome:** Out-of-sample spread rank IC, change in tax revenue, false alerts, distress recall. Stop if No incremental out-of-time predictive effect after socioeconomic covariates and issuer-selection controls..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
