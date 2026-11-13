# EVALS — Cleared Versus Tri-Party Repo Fragmentation Nowcast
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** A public-data fragmentation state predicts next-session tail moves in funding conditions beyond aggregate SOFR and repo volume.
- **Comparator:** SOFR level change and aggregate funding volume z-score..
- **Candidate:** State-space latent fragmentation index with lag-aware missingness..
- **Advanced alternative:** Hierarchical online change-point and causal regime attribution by venue and reporting channel..
- **Metrics:** next-session stress AUPRC, calibrated Brier score, false alarm rate, funding stress drawdown..
- **Stop/no-go:** Reject if lag-safe AUPRC does not exceed SOFR-only benchmark by 0.03 on an untouched crisis/quiet holdout.
- **Cost sensitivity:** USD $125k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $40k–$210k over 24 months. Net ROI = (gross benefit − cost)/cost = **-68% to 68%**. NOT forecast or historical measurement. Economic lever: scenario: avoid one or two large risk-buffer errors or reduce manual funding surveillance effort; no P&L is proven.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. risk update only after OFR release; cleared repo T+1 and tri-party T+2 availability; never use same-day unpublished values
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: An alert/risk-overlay product first; any later trade signal faces venue access, funding tenor and prices.
7. Stress identification risk: Revised/missing suppressed OFR cells and cross-venue holiday timing can create lookahead and artificial divergences.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
OFR release lag; missing-confidential cells; venue identifier regime changes; holiday calendars.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
