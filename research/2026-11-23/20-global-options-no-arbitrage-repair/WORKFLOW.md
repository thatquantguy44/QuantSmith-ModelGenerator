# WORKFLOW — Arbitrage-Free Equity Volatility Surface Repair Across Markets
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

1. **Domain:** US, UK and Japan equity index listed options; decision: Produce arbitrage-consistent option risk surfaces and screen put-call/calendar violations before risk budgeting..
2. **Source and licensing:** Cboe Historical Options Market Statistics, Cboe delayed options data restrictions are public starting points; Licensed cross-exchange historical option chains, forward curves and bid-ask depths is gated until entitlement.
3. **Temporal contract:** Quote timestamp aligned to each exchange session; repair uses no quotes from future or closed-market snapshots.
4. **Baseline:** Per-expiry unconstrained cubic interpolation with clip to bid/ask with full operational cost and feasible eligibility.
5. **Model:** Static no-arbitrage SVI/SSVI constrained calibration with conservative quote filters, then justify any additional complexity in Joint multi-market neural stochastic volatility calibrated to arbitrage constraints and holidays.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress American vs European option styles, dividend marks, early exercise, restricted historical quote rights..
7. **Outcome:** Static arbitrage violations, held-out option price MAE, hedge delta error, false anomaly alerts. Stop if Constrained repair does not reduce out-of-sample pricing/hedging error or introduces hidden quote crossings..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
