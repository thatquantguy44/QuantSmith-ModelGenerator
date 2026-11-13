# SOURCES — Cash-Collateral Reinvestment Liquidity Run-Off Controller
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [OFR U.S. Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) — daily aggregated rates/volumes; cleared generally T+1, tri-party generally T+2; missing values possible.
- [Brunnermeier–Pedersen, Market Liquidity and Funding Liquidity](https://doi.org/10.1093/rfs/hhn098) — peer-reviewed paper, conceptual context; not proof of proposed factor.
- [New York Fed Primary Dealer Statistics](https://www.newyorkfed.org/markets/primarydealers) — published weekly primary dealer aggregate statistics; not a dealer inventory feed.

**Suitability caveat:** Public SOFR and money-market rates can proxy the reinvestment curve, not private lending redemption behavior.

## 2. Licensed commercial data, only after contract and approval
Short-term instrument prices and redemption proxy data with proper licensing.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
Authorized program-level cash collateral investments, contractual restrictions and anonymized historical loan returns.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
Loan termination flows; collateral principal; reinvestment settlement and maturity ladders; redemption windows; eligible funds; short-term yields; stress scenarios. **Observation grain:** cash collateral program × reinvestment maturity bucket × business day. **Decision horizon:** end-of-day reinvestment decision with availability of prior published cash flow and eligible settlement windows.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
