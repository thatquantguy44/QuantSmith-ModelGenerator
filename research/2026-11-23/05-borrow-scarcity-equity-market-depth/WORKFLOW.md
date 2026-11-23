# WORKFLOW — Borrow Scarcity Causal Effect on Equity Market-Maker Quoted Depth
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

1. **Domain:** US equities and select developed markets; decision: Adjust financing risk capital for equity liquidity provision when short-sale borrow becomes scarce..
2. **Source and licensing:** SEC EDGAR Data Access are public starting points; LOBSTER/order book or exchange TAQ and securities-lending locates is gated until entitlement.
3. **Temporal contract:** Quote-decision timing after actual supply notice; event timestamps distinguish pre-event leak, regular session and close.
4. **Baseline:** Spread/depth forecasting using only realized volatility and market cap with full operational cost and feasible eligibility.
5. **Model:** Matched differences-in-differences/event-time instrumental analysis, then justify any additional complexity in Structural market-maker inventory equilibrium with dynamic borrowing constraint.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress Selection on distressed shorts, simultaneous volatility and hard-to-borrow endogenous events..
7. **Outcome:** Event-time β confidence interval, placebos, effective spread, depth and incremental risk price. Stop if No pre-registered effect with valid pretrends/instruments or effect only on illiquid untradeable names..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
