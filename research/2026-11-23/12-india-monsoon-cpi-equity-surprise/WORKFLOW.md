# WORKFLOW — India Monsoon Surprise to Food CPI and Local Equity Pricing
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

1. **Domain:** India, state agriculture, INR and Indian listed consumer equities; decision: Time/hedge exposures to monsoon-sensitive consumption and agriculture pricing after publicly available rainfall surprises..
2. **Source and licensing:** India Meteorological Department Rainfall Information, India OGD Rainfall History are public starting points; Historical NSE returns and detailed CPI release vintages is gated until entitlement.
3. **Temporal contract:** IMD publication timestamp and next-tradable-session; CPI only after official release, no revisions used retroactively.
4. **Baseline:** All-India seasonal rainfall deviation plus autoregressive food CPI with full operational cost and feasible eligibility.
5. **Model:** Hierarchical spatial distributed-lag regression + causal crop weighting, then justify any additional complexity in Weather-to-crop graph structural state-space model with uncertainty propagation.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress Historical IMD OGD resources lag, crop mix revisions, rainfall not yield and policy interventions..
7. **Outcome:** CPI MAE, sector neutral-return IC, hit rate net costs, seasonal robustness. Stop if No incremental holdout inflation forecast or stock-return effect against rainfall benchmark..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
