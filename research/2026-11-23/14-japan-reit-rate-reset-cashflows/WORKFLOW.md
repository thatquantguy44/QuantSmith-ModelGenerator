# WORKFLOW — Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization
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

1. **Domain:** Japan J-REITs and commercial real estate; decision: Distinguish J-REIT rate-reset liability timing and property yield spreads rather than duration-only price sensitivity..
2. **Source and licensing:** Bank of Japan Time-Series Data Search, SEC EDGAR Data Access are public starting points; TSE J-REIT historical prices and Japanese property rent indices is gated until entitlement.
3. **Temporal contract:** Use release/filing acceptance before BOJ event and timestamp debt disclosure versions.
4. **Baseline:** Market REIT index duration and price-to-NAV score with full operational cost and feasible eligibility.
5. **Model:** Disclosure-derived maturity-wall factor with event-based hedged return regressions, then justify any additional complexity in Tenant lease rollover and financing reset structural cash-flow model.
6. **Horizon:** pre-register holdout, embargo overlapping outcomes, stress Japanese disclosure translation/lease renewal timing and selective REIT survivorship..
7. **Outcome:** AFFO forecast error, sector-neutral return IC, liquidity-adjusted drawdown, event placebo. Stop if No incremental post-rate-shift forecast after issuer fixed-effects and NAV-duration controls..
8. **Review:** separate generated narrative, deterministic results, human signoff and optional shadow monitoring. No live trade path included.

**On any missing licence, timestamp or constraint return BLOCKED.**
