# SOURCES — AI Infrastructure Capex-to-Power-and-Export Supply Chain Factor
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [SEC EDGAR APIs](https://www.sec.gov/search-filings/edgar-application-programming-interfaces) — public filings and XBRL; use public dissemination timestamps.
- [EIA Open Data/API](https://www.eia.gov/opendata/) — hourly electricity series and energy fundamentals; registration/terms may apply.
- [UN Comtrade API documentation](https://comtradeplus.un.org/en/api-docs) — free preview limited to 500 rows; broader access and historical versions may require keys/premium.
- [Gu–Kelly–Xiu, Empirical Asset Pricing via Machine Learning](https://doi.org/10.1093/rfs/hhaa009) — peer-reviewed ML asset pricing benchmark framework.

**Suitability caveat:** SEC filing disclosures, EIA grid observations and UN Comtrade aggregate products; issuer-level mapping is research inference.

## 2. Licensed commercial data, only after contract and approval
Licensed earnings estimates, supply-chain relationship database, country index constituents and stock total returns.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
No required private data; avoid insider/project-specific procurement data.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
SEC EDGAR filed capital expenditure and commitments, EIA power demand/generation, public utility service-area reports, UN Comtrade semiconductor/electrical equipment trade. **Observation grain:** public company disclosure × filing-time vintage × geography × monthly energy/trade release. **Decision horizon:** rebalance monthly after latest public filings, energy updates and international trade release.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
