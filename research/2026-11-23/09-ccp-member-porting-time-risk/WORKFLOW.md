# WORKFLOW — CCP Member Default Position-Porting Time and Liquidity Optimization
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

1. **Domain:** Global cleared rates and repo portfolios; decision: Choose contingent porting routes and liquidity reserves for a hypothetical clearing-member default..
2. **Source and licensing:** DTCC FICC Mortgage-Backed Securities Division, BIS Basel III Monitoring Release, Sep 23 2026 are public starting points; Clearing member cost/risk reference agreements is gated until entitlement.
3. **Temporal contract:** Use rule versions effective on default scenario date, exclude assumptions from later CCP notices.
4. **Baseline:** Manual first-available eligible clearing member routing with full operational cost and feasible eligibility.
5. **Model:** Multi-period mixed-integer stochastic porting/survival flow simulator, then justify any additional complexity in Distributionally robust queueing network with correlated member liquidity and stress haircuts.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress Actual CCP porting legality and bilateral customer consents unknown, correlated failures may be unidentifiable..
7. **Outcome:** Porting completion by deadline, unmet margin, loss given port failure, rerouting overhead. Stop if No improvement in adverse default scenarios over conservative porting alternatives or reliance on forbidden client position data..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
