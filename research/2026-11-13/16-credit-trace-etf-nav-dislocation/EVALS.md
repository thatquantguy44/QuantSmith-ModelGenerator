# EVALS — Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** Publication-time TRACE liquidity dispersion predicts subsequent ETF tracking instability beyond ETF realized volatility and HY/IG spread levels.
- **Comparator:** ETF realized volatility and quoted bid-ask spread..
- **Candidate:** Robust bond-liquidity dispersion index and ETF tracking-state model..
- **Advanced alternative:** Structural ETF redemption/creation network with dealer intermediation bottlenecks..
- **Metrics:** tracking error forecast, credit tail loss, hedge slippage, redemption-state calibration..
- **Stop/no-go:** Reject if no incremental tracking error forecast or lower stress drawdown after NAV timestamp normalization and realistic ETF costs.
- **Cost sensitivity:** USD $215k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$455k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 112%**. NOT forecast or historical measurement. Economic lever: hypothetical $20m credit hedge program, saving a fraction of tracking-loss during rare liquidity events; no realized estimate.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. end-of-session / next-session ETF risk adjustment only; public aggregate data may not cover security-level historical panel
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Only liquid ETFs and hedges, no synthetic bond execution assuming NAV arbitrage.
7. Stress identification risk: Reported bond prices may be size-capped/delayed; TRACE trade access/licensing varies and NAV can embed stale marks.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
NAV timestamps; TRACE cap/missing trades; ETF constituent changes; survivor selection and index reconstitution.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
