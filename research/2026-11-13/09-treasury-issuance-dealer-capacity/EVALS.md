# EVALS — Treasury Issuance-to-Dealer Intermediation Capacity Map
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** Public auction-supply and weekly dealer-position innovations predict future Treasury liquidity stress more reliably than rate volatility alone.
- **Comparator:** Treasury yield volatility and calendar week indicators..
- **Candidate:** Event-study + state-space dealer supply absorption proxy..
- **Advanced alternative:** Instrumented quasi-experiment using prescheduled auction supply shocks and cross-CUSIP constraints..
- **Metrics:** stress forecast Brier, AUPRC, lead-time, false positives and hedge drawdown..
- **Stop/no-go:** Reject if no improvement over the rate-volatility-only benchmark on genuinely held-out issuance regimes.
- **Cost sensitivity:** USD $100k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $25k–$170k over 24 months. Net ROI = (gross benefit − cost)/cost = **-75% to 70%**. NOT forecast or historical measurement. Economic lever: scenario: one avoided bad inventory allocation month or improved hedging stress alerts; not a measured signal.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. weekly close after primary dealer publication; never treat reported prior-week positions as contemporaneous
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Public signal is a risk overlay; tradability needs actual Treasury order book, bid/ask, duration and repo access.
7. Stress identification risk: Aggregate dealer reports cannot identify securities or dealers and issuance is endogenous to financing conditions.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
report-date vs value-date; auction reopenings; benchmark rolls; stress-label embargo.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
