# WORKFLOW — Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral
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

1. **Domain:** Global banks; US/EU Basel liquidity reporting frameworks; decision: Allocate financing transactions by incremental liquidity-ratio headroom consumption, not only nominal repo spread..
2. **Source and licensing:** BIS Basel III Monitoring Release, Sep 23 2026, OFR US Repo Markets Data Release are public starting points; Executable secured funding curves and legal category taxonomies is gated until entitlement.
3. **Temporal contract:** Regulatory rule version, haircut classification and reporting entity apply as of funding decision.
4. **Baseline:** Rank repo offers by quoted rate subject to gross notional limits with full operational cost and feasible eligibility.
5. **Model:** Linear/mixed-integer secured funding allocation with LCR/NSFR dual-price attribution, then justify any additional complexity in Scenario-based shadow-price frontier with intraday and quarter-end liquidity risk.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress Entity-specific regulatory implementation and internal forecasts differ; cannot reconstruct actual LCR from public totals..
7. **Outcome:** All-in liquidity-adjusted cost, marginal dual price, buffer breaches, sensitivity to rule version. Stop if No cost difference over conservative liquidity-constrained benchmark or unstable/uninterpretable duals..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
