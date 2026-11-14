# SOURCES — US–Euro Sovereign Curve Shock Decomposition with Data Vintages
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [ECB Euro Area Yield Curves](https://www.ecb.europa.eu/stats/financial_markets_and_interest_rates/euro_area_yield_curves/html/index.en.html) — published euro-area benchmark yield curves; not executable bond prices.
- [FRED/ALFRED real-time vintage API documentation](https://fred.stlouisfed.org/docs/api/fred/realtime_period.html) — supports as-known-at historical macro vintages; series-specific release eligibility.
- [OECD SDMX API](https://www.oecd.org/en/data/insights/data-explainers/2024/09/api.html) — free economic data with revisions, publication lags and API terms.
- [Moskowitz–Ooi–Pedersen, Time Series Momentum](https://doi.org/10.1016/j.jfineco.2011.11.003) — published multi-asset benchmark, not evidence for specific new idea.

**Suitability caveat:** ECB and FRED provide curves/vintages but not executable futures bid/ask or consensus expectation snapshots.

## 2. Licensed commercial data, only after contract and approval
Timestamped macro consensus, Treasury/Bund futures quotes and instrument rolls.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
No required private inputs.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
ECB published euro yield curve, US yields and ALFRED macro vintages, official release times, FX hedges, rates futures cost. **Observation grain:** economic release event × curve tenor × publication instant × geography. **Decision horizon:** end-of-release or next-session decision after releases disseminate; avoid falsely assuming instant access to revised series.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
