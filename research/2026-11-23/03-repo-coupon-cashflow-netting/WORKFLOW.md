# WORKFLOW — Repo Coupon and Principal Event Cash-Flow Netting Scheduler
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

1. **Domain:** US Treasuries, agencies and multi-currency repo; decision: Minimize same-day cash deficits caused by collateral coupon/principal flows and contractual manufactured payments..
2. **Source and licensing:** New York Fed Primary Dealer Statistics, SEC EDGAR Data Access are public starting points; Securities master coupon and settlement event feeds is gated until entitlement.
3. **Temporal contract:** Coupon schedule published at issuance; adjustments and confirmed obligations only after contract notice timestamp.
4. **Baseline:** Gross independent payment processing with static buffer with full operational cost and feasible eligibility.
5. **Model:** Mixed-integer liquidity scheduling with eligibility/netting-set constraints, then justify any additional complexity in Stochastic event-flow MPC with missed payment penalties and legal-entity netting restrictions.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress Wrong beneficial-ownership treatment, netting rights and special cash settlement terms..
7. **Outcome:** Peak cash buffer, gross payment count, exception cost, settlement timeliness. Stop if No capacity-adjusted cost reduction versus pre-netted conventional operations or violations of payment rights..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
