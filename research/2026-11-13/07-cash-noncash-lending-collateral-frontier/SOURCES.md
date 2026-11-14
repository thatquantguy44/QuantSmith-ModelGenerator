# SOURCES — Cash versus Noncash Loan-Collateral Economic Frontier
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [OFR U.S. Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) — daily aggregated rates/volumes; cleared generally T+1, tri-party generally T+2; missing values possible.
- [New York Fed SOMA Securities Lending](https://www.newyorkfed.org/markets/domestic-market-operations/monetary-policy-implementation/securities-lending) — public operation auction results; not broad securities-lending fee market.
- [Brunnermeier–Pedersen, Market Liquidity and Funding Liquidity](https://doi.org/10.1093/rfs/hhn098) — peer-reviewed paper, conceptual context; not proof of proposed factor.

**Suitability caveat:** Official repo market rates provide funding context; collateral-type price schedules are program-specific.

## 2. Licensed commercial data, only after contract and approval
Commercial securities-lending fee/borrower collateral benchmark datasets.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
Mandate-approved collateral schedules, borrower contracts and actual rebate/fee quotes.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
Cash and noncash terms, rebate schedules, reinvestment constraints, asset eligibility, mark-to-market, haircuts and legal restrictions. **Observation grain:** loan offer × collateral type × owner mandate × quotation timestamp. **Decision horizon:** quote acceptance before loan opening with known collateral terms, not end-of-day realized earnings.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
