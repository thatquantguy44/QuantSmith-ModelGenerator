# SOURCES — Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [FINRA TRACE overview](https://syndication.finra.org/content/what-trace-and-how-can-it-help-me) — public trades/aggregates; full historical bond-level feeds may be licensed.
- [Haddad–Moreira–Muir, When Selling Becomes Viral](https://www.nber.org/papers/w27168) — working paper on market distress and fixed-income market dysfunction.
- [Gu–Kelly–Xiu, Empirical Asset Pricing via Machine Learning](https://doi.org/10.1093/rfs/hhaa009) — peer-reviewed ML asset pricing benchmark framework.

**Suitability caveat:** FINRA explains TRACE reporting and offers public aggregates; institutional historical tick panels may require subscription.

## 2. Licensed commercial data, only after contract and approval
Full historic TRACE and ETF NAV indicative basket/creation data; licensed CDX/credit curves.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
No private holdings required; market-maker basket information only with approval.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
FINRA TRACE public aggregate/trade pages, subscription historical bond records, ETF market prices, NAV timestamps, bond indices, CDX basis. **Observation grain:** bond × disseminated trade timestamp × ETF NAV publication timestamp. **Decision horizon:** end-of-session / next-session ETF risk adjustment only; public aggregate data may not cover security-level historical panel.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
