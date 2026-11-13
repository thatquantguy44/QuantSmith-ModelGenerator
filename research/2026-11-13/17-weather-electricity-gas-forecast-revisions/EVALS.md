# EVALS — Weather Forecast Revision as an Electricity-to-Gas Risk Hedge
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** Timestamped forecast *revisions* explain next-session electricity net-load stress better than absolute forecast temperature or seasonal normals.
- **Comparator:** Seasonal degree-day demand regression and absolute temperature forecasts..
- **Candidate:** Net-load forecast-revision elasticity with non-linear stress threshold..
- **Advanced alternative:** Probabilistic shortfall-and-constraint model with weather ensemble calibration..
- **Metrics:** load p95 quantile loss, probabilistic calibration, hedge tracking error, net futures carry..
- **Stop/no-go:** Reject if no improvements in forecast quantile loss or hedge after-cost variance over degrees-day baseline.
- **Cost sensitivity:** USD $170k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$470k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 176%**. NOT forecast or historical measurement. Economic lever: hypothetical $10m energy risk sleeve with 0–235 bps annualized risk/carry improvements; outcomes uncertain.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. forecast issuance is the earliest legal decision; never consume later realized weather or EIA actual load before release
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Trade via highly liquid gas futures or energy equity baskets, with geographic basis and sector beta mismatch priced.
7. Stress identification risk: Archive of *historical forecasts as issued* may be inaccessible; today's historical observations are not contemporaneous forecasts.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
no actual-weather lookahead; daylight saving hour repeat; region changes; forecast issue and EIA publish lag.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
