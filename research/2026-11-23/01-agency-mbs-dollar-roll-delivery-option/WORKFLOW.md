# WORKFLOW — Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option
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

1. **Domain:** United States / agency MBS TBA; decision: Select TBA dollar-roll financing and permissible pool delivery sets versus holding specified pools financed through repo..
2. **Source and licensing:** DTCC FICC Mortgage-Backed Securities Division, DTCC Electronic Pool Notification are public starting points; Executable TBA rolls, specified-pool prices, MBS prepayment factors is gated until entitlement.
3. **Temporal contract:** Decision at pre-roll executable quote; EPN pool assignment becomes known later and must not leak into earlier signals.
4. **Baseline:** Dollar-roll implied financing vs same-tenor generic repo without delivery-option valuation with full operational cost and feasible eligibility.
5. **Model:** Constrained pool-delivery optimizer with observable pool financing carry and roll prices, then justify any additional complexity in Stochastic pool quality and delivery-selection real-options game with cheapest-deliverable simulation.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress Pool price selection, payup optionality, actual pool availability and post-trade EPN leakage..
7. **Outcome:** Net financing bps, cheapest-deliverable premium, pre-settlement fail exposure, netted capital and tail regret. Stop if No stable out-of-sample cost-adjusted advantage over delivery-aware manual baseline at realistic pool eligibility..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
