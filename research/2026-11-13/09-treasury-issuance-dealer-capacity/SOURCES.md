# SOURCES — Treasury Issuance-to-Dealer Intermediation Capacity Map
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [New York Fed Primary Dealer Statistics](https://www.newyorkfed.org/markets/primarydealers) — published weekly primary dealer aggregate statistics; not a dealer inventory feed.
- [OFR Primary Dealer Statistics data](https://www.financialresearch.gov/short-term-funding-monitor/datasets/nypd/) — public weekly dealer financing/fail aggregates; not specific participants.
- [OFR U.S. Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) — daily aggregated rates/volumes; cleared generally T+1, tri-party generally T+2; missing values possible.
- [SEC Treasury Clearing Implementation](https://www.sec.gov/featured-topics/treasury-clearing-implementation) — regulatory guidance, not a trade-level dataset.

**Suitability caveat:** Treasury and NY Fed release events and dealer statistics publicly, though publication lags must be retained.

## 2. Licensed commercial data, only after contract and approval
CUSIP prices and Treasury bond quote/liquidity microstructure.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
Optional firm-specific inventory and spread exposures for private validation.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
Treasury auction issuance and settlement schedule; weekly primary dealer net positions/financing; OFR repo aggregates; public Treasury yield changes. **Observation grain:** issuance cohort × week of publicly released dealer aggregates. **Decision horizon:** weekly close after primary dealer publication; never treat reported prior-week positions as contemporaneous.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
