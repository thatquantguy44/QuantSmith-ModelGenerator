# WORKFLOW — Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
```mermaid
flowchart LR
 A[Hypothesis and market choice] --> B[License and event clock]
 B --> C[Point-in-time panel]
 C --> D[Feasible costed baseline]
 D --> E[Candidate model]
 E --> F[Chronological holdout]
 F --> G{Falsification gate}
 G -->|Fail| H[Archive negative result]
 G -->|Pass| I[Capacity and risk audit]
 I --> J[Human shadow approval]
```

## Ordered workflow
**1. Ask a testable question:** Publication-time TRACE liquidity dispersion predicts subsequent ETF tracking instability beyond ETF realized volatility and HY/IG spread levels.
**2. Set the decision:** Hedge credit ETF risk in periods of underlying bond liquidity deterioration without assuming stale NAV is executable.
**3. Acquire data:** FINRA TRACE public aggregate/trade pages, subscription historical bond records, ETF market prices, NAV timestamps, bond indices, CDX basis.
**4. Freeze the temporal boundary:** end-of-session / next-session ETF risk adjustment only; public aggregate data may not cover security-level historical panel
**5. Run baseline:** ETF realized volatility and quoted bid-ask spread.
**6. Evaluate candidate:** Robust bond-liquidity dispersion index and ETF tracking-state model.
**7. Challenge method:** Structural ETF redemption/creation network with dealer intermediation bottlenecks., only if justified.
**8. Measure:** tracking error forecast, credit tail loss, hedge slippage, redemption-state calibration.
**9. Stress:** Reported bond prices may be size-capped/delayed; TRACE trade access/licensing varies and NAV can embed stale marks.
**10. Fail/continue rule:** Reject if no incremental tracking error forecast or lower stress drawdown after NAV timestamp normalization and realistic ETF costs.

For every failed gate record what was unavailable and why. All described execution stages are research plans, not completed model runs.
