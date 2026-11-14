# EVALS — Macro-Vintage Integrity Engine with Prediction Abstention
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** A vintage-aware abstention gate reduces false active signals and revisional backtest overstatement versus always-on macro factor models.
- **Comparator:** Always-on macro momentum score built from latest-vintage series..
- **Candidate:** As-of macro feature store with release-confidence model and abstention..
- **Advanced alternative:** Bayesian missing-data multiple-vintage filtering and conformal selective prediction with capacity-aware portfolio overlay..
- **Metrics:** revision-induced backtest bias, selective risk loss, coverage, false alarm rate, time-to-data-availability..
- **Stop/no-go:** Reject if abstention fails to reduce loss on corrected vintage history or simply abstains from all market decisions.
- **Cost sensitivity:** USD $130k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $20k–$245k over 24 months. Net ROI = (gross benefit − cost)/cost = **-85% to 88%**. NOT forecast or historical measurement. Economic lever: scenario: reduce failed model deployment and wasted model-validation hours, plus any trading uplift; 24-month benefits unmeasured.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. update only after first verified public release; revisions must enter as new events, not retroactively
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Primarily a reusable research data-quality service; alpha/executable returns need licensed market backtest.
7. Stress identification risk: ALFRED historical series coverage, future revisions and OECD methodological breaks can be incomplete; abstention selection bias.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
revision as-of join; missing first release; method breaks; abstain-all negative control.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
