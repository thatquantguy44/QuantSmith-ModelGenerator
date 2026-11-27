# WORKFLOW — Corporate Bond Securities Lending from CDS Basis Hedge Demand
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

1. **Domain:** US and European investment-grade / high-yield credit; decision: Allocate bond lending supply to CDS-bond basis hedging demand with counterparty and liquidity limits..
2. **Source and licensing:** SEC EDGAR Data Access, New York Fed Primary Dealer Statistics are public starting points; Corporate bond TRACE histories, CDS quotes and bond lending locates is gated until entitlement.
3. **Temporal contract:** CDS and cash-bond spreads only after published executable quote times; lending fills observed subsequently.
4. **Baseline:** Trailing borrower request count and issue-size utilization with full operational cost and feasible eligibility.
5. **Model:** Matched event study plus borrow-arrival hazard conditional on CDS-bond basis, then justify any additional complexity in Structural joint CDS/bond market-maker inventory model with selection-corrected demand.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress Non-executable CDS quotes, bond TRACE delay and endogeneity of credit distress..
7. **Outcome:** Borrow-arrival log score, realized net fee improvement, stale quote rate and borrow supply capacity. Stop if Estimated basis effects fail paired holdouts or increase rejected locates after slippage and liquidity controls..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
