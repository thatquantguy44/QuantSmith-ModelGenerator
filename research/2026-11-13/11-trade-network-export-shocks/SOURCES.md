# SOURCES — Trade-Network Export-Shock Transmission to Equity Sectors
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [UN Comtrade API documentation](https://comtradeplus.un.org/en/api-docs) — free preview limited to 500 rows; broader access and historical versions may require keys/premium.
- [OECD SDMX API](https://www.oecd.org/en/data/insights/data-explainers/2024/09/api.html) — free economic data with revisions, publication lags and API terms.
- [Gu–Kelly–Xiu, Empirical Asset Pricing via Machine Learning](https://doi.org/10.1093/rfs/hhaa009) — peer-reviewed ML asset pricing benchmark framework.

**Suitability caveat:** UN Comtrade public preview has limited records; full historical coverage may require free keyed or premium bulk access.

## 2. Licensed commercial data, only after contract and approval
Licensed country-sector total returns, revenue segment exposures and comprehensive Comtrade extracts.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
No required private information; optional approved broker execution/cost data only.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
UN Comtrade reported and partner-reported trade by HS code/month; sector country revenue mix; FX; sector returns and macro controls. **Observation grain:** reporter × partner × HS code × reference month × publication/availability timestamp. **Decision horizon:** monthly after trade report publication and revision; NEVER trade at reference-month timestamp.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
