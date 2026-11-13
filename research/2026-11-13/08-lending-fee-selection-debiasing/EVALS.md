# EVALS — Securities-Lending Fee Observability & Selection-Bias Corrector
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** Explicit observability weighting and partial identification shrink apparent fee benchmark error versus sample-weighted means on contributor holdouts.
- **Comparator:** Daily equally weighted or outstanding-value-weighted observed market fees..
- **Candidate:** Doubly robust weighting with overlap and selection-sensitivity intervals..
- **Advanced alternative:** Bayesian selection model with unverifiable missing-not-at-random stress bounds..
- **Metrics:** cross-contributor benchmark error, interval coverage, abstention, quote drift, market breadth coverage..
- **Stop/no-go:** Reject if cross-contributor MAE reduction <10% or intervals under-cover known withheld contributions.
- **Cost sensitivity:** USD $120k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $45k–$230k over 24 months. Net ROI = (gross benefit − cost)/cost = **-62% to 92%**. NOT forecast or historical measurement. Economic lever: scenario: avoid mispriced lending quotes on a small subset of specials; savings not inferable from the public sources alone.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. benchmark at next published cutoff; never use end-of-day contributions before receipt
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Primarily an internal benchmark/data product; no automatic quoting when source coverage or liquidity is inadequate.
7. Stress identification risk: Missing-not-at-random selection cannot be identified from executed loans alone; confidence intervals can be falsely narrow.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
extreme weights, overlap failure, withheld-vendor benchmark, late contribution leakage.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
