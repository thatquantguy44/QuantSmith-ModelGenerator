# SOURCES — Macro-Vintage Integrity Engine with Prediction Abstention
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [FRED/ALFRED real-time vintage API documentation](https://fred.stlouisfed.org/docs/api/fred/realtime_period.html) — supports as-known-at historical macro vintages; series-specific release eligibility.
- [OECD SDMX API](https://www.oecd.org/en/data/insights/data-explainers/2024/09/api.html) — free economic data with revisions, publication lags and API terms.
- [ECB Euro Area Yield Curves](https://www.ecb.europa.eu/stats/financial_markets_and_interest_rates/euro_area_yield_curves/html/index.en.html) — published euro-area benchmark yield curves; not executable bond prices.
- [Gu–Kelly–Xiu, Empirical Asset Pricing via Machine Learning](https://doi.org/10.1093/rfs/hhaa009) — peer-reviewed ML asset pricing benchmark framework.

**Suitability caveat:** FRED real-time API explicitly supports known-as-of periods; series availability and revision dates require series-specific verification.

## 2. Licensed commercial data, only after contract and approval
Timestamped institutional macro-surprise and market execution data if transformed into a strategy.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
No private data required.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
ALFRED historical revisions, ECB yield releases, OECD SDMX data vintage calendars, US/global market proxies. **Observation grain:** economic indicator × observation period × release date × vintage ID. **Decision horizon:** update only after first verified public release; revisions must enter as new events, not retroactively.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
