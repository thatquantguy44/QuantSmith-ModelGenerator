# SOURCES — Treasury Clearing Access-Path & Duplicate-Margin Optimizer
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [SEC Treasury Clearing Implementation](https://www.sec.gov/featured-topics/treasury-clearing-implementation) — regulatory guidance, not a trade-level dataset.
- [DTCC US Treasury Clearing](https://www.dtcc.com/initiatives/ustclearing) — clearing model and published aggregate information, not participant margin files.
- [OFR U.S. Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) — daily aggregated rates/volumes; cleared generally T+1, tri-party generally T+2; missing values possible.
- [Brunnermeier–Pedersen, Market Liquidity and Funding Liquidity](https://doi.org/10.1093/rfs/hhn098) — peer-reviewed paper, conceptual context; not proof of proposed factor.

**Suitability caveat:** SEC and DTCC rules describe access but do not provide participant-specific margin or allocation cost.

## 2. Licensed commercial data, only after contract and approval
Licensable transaction/quote history, margin-model input services and settlement reference data.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
Approved entity-specific FICC margin, default-fund allocation, liquidity, contracts and clearing quotes (never public repo).
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
Eligible trade templates; path availability; historical quote spreads; initial/variation margin stress; capital/CCLF allocation; modeled netting sets; direct/sponsored/agent fees. **Observation grain:** trade × eligible clearing access path × decision timestamp. **Decision horizon:** trade routing decision at quote acceptance; historical public aggregates are lagged and cannot be used as intraday quotes.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
