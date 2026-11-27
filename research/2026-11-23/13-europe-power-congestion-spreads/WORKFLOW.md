# WORKFLOW — European Interconnector Congestion Power-Spread State Estimator
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

1. **Domain:** France, Germany, Benelux, Nordic and Iberian bidding zones; decision: Select hedged cross-zone power spread exposures conditional on public transfer constraints..
2. **Source and licensing:** ENTSO-E Transparency Platform File Library Guide, Oct 9 2026, US EIA Public API are public starting points; Executable EPEX/ICE forward curves and interconnector rights prices is gated until entitlement.
3. **Temporal contract:** Only ENTSO-E forecasts published before day-ahead bidding deadline; actual flows/prices are evaluation targets.
4. **Baseline:** Historical seasonal hourly spread by zone pair with full operational cost and feasible eligibility.
5. **Model:** Physical-congestion regime HMM with capacity-constrained exposure mapper, then justify any additional complexity in Stochastic DC power flow and multi-region graph forecasts with out-of-area transfer shadow prices.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress Cross-zone transmission rights and operational capacities not freely tradable; timestamps and price revisions..
7. **Outcome:** Congestion regime Brier score, spread MAE, feasible net hedge carry and stress CVaR. Stop if Spread gains disappear after simultaneous public forecast access, congestion settlement and capacity rights..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
