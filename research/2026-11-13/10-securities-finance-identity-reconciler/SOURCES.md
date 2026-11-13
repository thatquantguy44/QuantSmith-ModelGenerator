# SOURCES — Cross-Book Securities Finance Identity Reconciliation Graph
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [OFR U.S. Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) — daily aggregated rates/volumes; cleared generally T+1, tri-party generally T+2; missing values possible.
- [New York Fed Primary Dealer Statistics](https://www.newyorkfed.org/markets/primarydealers) — published weekly primary dealer aggregate statistics; not a dealer inventory feed.
- [SEC Treasury Clearing Implementation](https://www.sec.gov/featured-topics/treasury-clearing-implementation) — regulatory guidance, not a trade-level dataset.

**Suitability caveat:** Official definitions guide field semantics, but real records remain private; publish only synthetic fixtures.

## 2. Licensed commercial data, only after contract and approval
Reference security master/LEI mappings licensed from vendors, where legally permitted.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
Firm transaction IDs, ownership and customer identifiers must never enter public artifacts.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
Synthetic records containing lifecycle events, ISIN/CUSIP, product type, settlement date, amount, counterparty alias and amendment chain. **Observation grain:** source record × canonical candidate × event version × timestamp. **Decision horizon:** real-time/overnight reconciliation; no future correction can be applied retroactively to a prior risk snapshot.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
