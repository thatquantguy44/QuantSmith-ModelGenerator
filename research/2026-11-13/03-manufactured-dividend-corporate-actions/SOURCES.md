# SOURCES — Manufactured-Dividend and Corporate-Action Loan Economics
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [SEC EDGAR APIs](https://www.sec.gov/search-filings/edgar-application-programming-interfaces) — public filings and XBRL; use public dissemination timestamps.
- [New York Fed SOMA Securities Lending](https://www.newyorkfed.org/markets/domestic-market-operations/monetary-policy-implementation/securities-lending) — public operation auction results; not broad securities-lending fee market.
- [SEC Treasury Clearing Implementation](https://www.sec.gov/featured-topics/treasury-clearing-implementation) — regulatory guidance, not a trade-level dataset.

**Suitability caveat:** Public filings can anchor event timelines, but loan, tax and owner entitlement data are nonpublic.

## 2. Licensed commercial data, only after contract and approval
Corporate-action master, dividend forecast and withholding/tax reference service with licensed rights.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
Approved lender agreement, tax advisory decisions, loan positions and cash event ledger (not included).
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
Ex/record/pay dates; loan life; fee accrual; event elections; dividend amounts; owner tax flags and permitted return/recall rules. **Observation grain:** security × beneficial owner program × corporate-action event × decision timestamp. **Decision horizon:** event decisions before ex-date cutoff, using only announced corporate actions and approved tax interpretations then available.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
