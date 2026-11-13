# EVALS — Cash versus Noncash Loan-Collateral Economic Frontier
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** An all-in haircut, rebate and risk-adjusted price frontier improves loan profitability versus fee-only collateral preference.
- **Comparator:** Choose the highest headline loan spread among eligible offers..
- **Candidate:** Loan-specific all-in economic break-even and constraints solver..
- **Advanced alternative:** Robust multi-asset collateral frontier with convex liquidity tail-risk charge..
- **Metrics:** net economic revenue, risk capital per dollar, haircuts and eligibility breaches, retained lending volume..
- **Stop/no-go:** Reject if no incremental cost-adjusted profit after retaining legally admissible and service-quality constraints.
- **Cost sensitivity:** USD $185k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $70k–$395k over 24 months. Net ROI = (gross benefit − cost)/cost = **-62% to 114%**. NOT forecast or historical measurement. Economic lever: assume feasible switch of a small subset of a $400m average lending pool at 3–12 bps all-in uplift (unverified).

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. quote acceptance before loan opening with known collateral terms, not end-of-day realized earnings
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Constrained by approved collateral classes, reinvestment capacity, borrower credit and liquidity.
7. Stress identification risk: Comparing unavailable cash reinvestment yield to executable noncash economics creates phantom spread.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
cash/noncash double-count; currency basis; disallowed rehypothecation; conditional rebate reset.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
