# SOURCES — Securities-Lending Fee Observability & Selection-Bias Corrector
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [New York Fed SOMA Securities Lending](https://www.newyorkfed.org/markets/domestic-market-operations/monetary-policy-implementation/securities-lending) — public operation auction results; not broad securities-lending fee market.
- [New York Fed Primary Dealer Statistics](https://www.newyorkfed.org/markets/primarydealers) — published weekly primary dealer aggregate statistics; not a dealer inventory feed.
- [Brunnermeier–Pedersen, Market Liquidity and Funding Liquidity](https://doi.org/10.1093/rfs/hhn098) — peer-reviewed paper, conceptual context; not proof of proposed factor.

**Suitability caveat:** Public security market data can inform context, but no complete free securities-loan execution tape is assumed.

## 2. Licensed commercial data, only after contract and approval
Licensed securities-lending contribution feeds from multiple independent vendors.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
Permissioned quote/locate contributor provenance and approved historical fee observations.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
Contributed executed fee samples; public security volume/short-interest proxies; locate response metadata; source coverage and revisions. **Observation grain:** security × lending day × vendor/contributor population. **Decision horizon:** benchmark at next published cutoff; never use end-of-day contributions before receipt.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
