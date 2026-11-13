# EVALS — Cash-Collateral Reinvestment Liquidity Run-Off Controller
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** State-dependent loan run-off and reinvestment ladder simulation lowers liquidity shortfall probability versus static maturity and expected-return assumptions.
- **Comparator:** Static liquidity buffer plus duration/weighted average life constraints..
- **Candidate:** Conditional run-off survival model combined with stochastic cash-flow gap optimizer..
- **Advanced alternative:** Distributionally robust multi-period policy with borrower return clustering and fire-sale haircuts..
- **Metrics:** 99% liquidity shortfall, reinvestment net yield, liquidity carry, stressed liquidations, breach count..
- **Stop/no-go:** Reject if stress shortfalls are not reduced by at least 10% without degrading contractual yield or creating maturity breaches.
- **Cost sensitivity:** USD $190k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $80k–$390k over 24 months. Net ROI = (gross benefit − cost)/cost = **-58% to 105%**. NOT forecast or historical measurement. Economic lever: hypothetical $600m collateral pool; avoid 1–5 days of emergency liquidity costs in a 24-month horizon; benefits depend on realized stress frequencies.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. end-of-day reinvestment decision with availability of prior published cash flow and eligible settlement windows
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Capital is constrained by contractual permissible instruments, concentration, tenor limits and financing market depth.
7. Stress identification risk: Return flows may cluster under crises; survivorship of reinvestment balances causes understated withdrawals.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
negative cash after returns; same-day maturity cutoffs; concentration; incorrect day-count conventions.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
