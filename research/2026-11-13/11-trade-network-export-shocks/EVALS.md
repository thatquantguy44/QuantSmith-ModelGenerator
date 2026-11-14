# EVALS — Trade-Network Export-Shock Transmission to Equity Sectors
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** Lag-aware product-network shocks identify medium-horizon cross-country sector earnings surprises beyond FX and industrial production.
- **Comparator:** Equal-weight country sector allocation with FX and local industrial production controls..
- **Candidate:** Sparse directed trade graph factor with event-lag-aware regressions..
- **Advanced alternative:** Causal graph neural propagation with hard release-vintage masking and sector earnings transmission..
- **Metrics:** OOS sector information coefficient, dollar-neutral Sharpe, earnings revision hit rate, turnover and tail loss..
- **Stop/no-go:** Reject if positive net cross-country IC is not stable in each of two disjoint geographic holdouts or after publication lags.
- **Cost sensitivity:** USD $150k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$520k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 247%**. NOT forecast or historical measurement. Economic lever: hypothetical $10m liquid sector sleeve and 0–260 bps gross annualized alpha capture over 2 years; zero base benefit is plausible.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. monthly after trade report publication and revision; NEVER trade at reference-month timestamp
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: ETFs and liquid futures only for first implementation; portfolio turnover caps and country exposure floors.
7. Stress identification risk: Revisions, late reporters, trade re-exports and mapping HS codes to listed firms can create survivorship and spurious exposure.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
release-time embargo, HS classification revisions, reexports double count, country coverage attrition.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
