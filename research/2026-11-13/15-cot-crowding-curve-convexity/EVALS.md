# EVALS — CFTC Positioning Concentration and Commodity Curve Convexity
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** CFTC public trader-category concentration interacts with futures curve slope/convexity to forecast downside tail asymmetry better than carry alone.
- **Comparator:** Futures curve carry/roll-yield and 12-month time-series momentum..
- **Candidate:** Positioning-conditioned conditional expected shortfall regression..
- **Advanced alternative:** Stochastic inventory-demand equilibrium with nonlinear dealer hedging and curve impact..
- **Metrics:** tail loss reduction, annualized Sharpe after roll/slippage, opportunity-cost drag and hedge stability..
- **Stop/no-go:** Reject if tail-risk control does not beat carry/momentum or negative convexity effect changes sign in out-of-sample contracts.
- **Cost sensitivity:** USD $105k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$250k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 138%**. NOT forecast or historical measurement. Economic lever: hypothetical $20m risk budget, small tail-loss reduction in commodity futures over 24 months; benefits uncertain.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. earliest action is CFTC publication/next executable session; no use of Tuesday positions on Tuesday
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Enforce futures open interest participation cap, roll liquidity and margin stress; no physical commodity positions.
7. Stress identification risk: CFTC taxonomy changes, combined report double-counting and slow publication may annihilate predictive edge.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
Tuesday/Friday information boundary; contract taxonomy changes; no lookahead rolls; back-adjustment robustness.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
