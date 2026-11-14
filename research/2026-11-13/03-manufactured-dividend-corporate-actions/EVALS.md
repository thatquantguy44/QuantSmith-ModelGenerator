# EVALS — Manufactured-Dividend and Corporate-Action Loan Economics
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** Event-time aware loan optimization removes avoidable payment/operational leakage relative to fee-only renewal rules while remaining faithful to tax/legal restrictions.
- **Comparator:** Renew if lending fee remains positive and return only upon explicit mandatory recall..
- **Candidate:** Rule-checked event economics and constrained loan life-cycle integer optimizer..
- **Advanced alternative:** Scenario tree for unresolved election announcements and corporate action adjustment ranges..
- **Metrics:** net program income, missed payment events, operational exceptions, unauthorized action count..
- **Stop/no-go:** Reject if post-cost incremental program income is nonpositive or event-aware policy increases mandatory-payment exceptions.
- **Cost sensitivity:** USD $150k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $45k–$310k over 24 months. Net ROI = (gross benefit − cost)/cost = **-70% to 107%**. NOT forecast or historical measurement. Economic lever: illustrative prevention of a small number of high-value event-payment exceptions and legal-allowable tax drag over two years.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. event decisions before ex-date cutoff, using only announced corporate actions and approved tax interpretations then available
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Only owner-permitted loans and action windows; supply cannot be fabricated by the optimizer.
7. Stress identification risk: Tax withholding, treaty benefits and manufactured-dividend treatment cannot be assumed from issuer-country information alone.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
record/ex-date ordering; mandatory election priority; FX conversion; tax flag unknown must block.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
