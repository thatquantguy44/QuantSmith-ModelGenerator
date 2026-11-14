# SOURCES — Settlement-Fail Buy-In versus Wait Optimal Stopping
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [OFR Primary Dealer Statistics data](https://www.financialresearch.gov/short-term-funding-monitor/datasets/nypd/) — public weekly dealer financing/fail aggregates; not specific participants.
- [New York Fed Primary Dealer Statistics](https://www.newyorkfed.org/markets/primarydealers) — published weekly primary dealer aggregate statistics; not a dealer inventory feed.
- [Brunnermeier–Pedersen, Market Liquidity and Funding Liquidity](https://doi.org/10.1093/rfs/hhn098) — peer-reviewed paper, conceptual context; not proof of proposed factor.

**Suitability caveat:** Primary dealer fails are aggregate benchmarks, not individual securities or cost histories.

## 2. Licensed commercial data, only after contract and approval
Licensed dealer fail/cover reference prices and settlement clock information.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
Actual failed positions, buy-in legal clauses and counterparty settlement timelines in approved environment.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
Public dealer failure aggregates for calibration; synthetic failure life histories; approved buy-in quotes, fails charges and legal remedies. **Observation grain:** failed settlement instruction × elapsed failed day × cut-off timestamp. **Decision horizon:** business-day cure decisions only after confirmed fail and remedy eligibility.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
