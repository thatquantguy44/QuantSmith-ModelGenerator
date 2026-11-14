# SOURCES — Tri-Party Collateral Eligibility Clause-to-Constraint Compiler
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [SEC Treasury Clearing Implementation](https://www.sec.gov/featured-topics/treasury-clearing-implementation) — regulatory guidance, not a trade-level dataset.
- [DTCC US Treasury Clearing](https://www.dtcc.com/initiatives/ustclearing) — clearing model and published aggregate information, not participant margin files.
- [OFR U.S. Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) — daily aggregated rates/volumes; cleared generally T+1, tri-party generally T+2; missing values possible.

**Suitability caveat:** Public clearing and securities-financing guidance gives domain patterns but not private triparty legal schedules.

## 2. Licensed commercial data, only after contract and approval
Licensed law/contract taxonomy and vendor eligibility schedules, if permitted.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
Private agreements, counsel-approved interpretations and security-master mappings; never commit contents.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
Synthetic collateral schedules; asset master; rating/issuer; eligibility categories; haircut tables; human-labeled clause examples. **Observation grain:** contract clause × effective version × collateral asset × valuation time. **Decision horizon:** rules valid at collateral decision; amendments apply from legal effective date, not document creation date.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
