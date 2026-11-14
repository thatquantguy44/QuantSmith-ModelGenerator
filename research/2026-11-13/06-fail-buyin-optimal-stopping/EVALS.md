# EVALS — Settlement-Fail Buy-In versus Wait Optimal Stopping
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** A time-to-cure policy using fail penalties and executable cover costs lowers realized failure resolution expense versus fixed escalation cutoffs.
- **Comparator:** Auto-escalate after fixed N-day failure age..
- **Candidate:** Discrete-time survival model with exact dynamic-programming stopping rule..
- **Advanced alternative:** Partial-observation optimal stopping with supply scarcity and stochastic cover price..
- **Metrics:** resolved failure days, total cure cost, forced buy-in count, missed deadline, tail loss..
- **Stop/no-go:** Reject if holdout cost savings are below 5% or any mandated deadline is missed.
- **Cost sensitivity:** USD $130k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $65k–$260k over 24 months. Net ROI = (gross benefit − cost)/cost = **-50% to 100%**. NOT forecast or historical measurement. Economic lever: scenario: fewer unnecessary emergency cover trades on an illustrative $150m failed notional portfolio over two years.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. business-day cure decisions only after confirmed fail and remedy eligibility
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Limited by available deliverable security and realistic executable cover bids.
7. Stress identification risk: Fails charges and rights to enforce buy-ins differ by asset, market and contract; wrong assumptions invalidate decisions.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
weekend elapsed-time logic; emergency close-out overrides; no same-day future fill information.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
