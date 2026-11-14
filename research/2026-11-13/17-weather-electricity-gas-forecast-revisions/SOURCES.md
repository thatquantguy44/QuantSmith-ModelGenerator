# SOURCES — Weather Forecast Revision as an Electricity-to-Gas Risk Hedge
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [US National Weather Service API](https://www.weather.gov/documentation/services-web-api) — public forecasts/alerts/observations; respect rate limits and issuance times.
- [EIA Open Data/API](https://www.eia.gov/opendata/) — hourly electricity series and energy fundamentals; registration/terms may apply.
- [NOAA historical climate datasets](https://www.ncei.noaa.gov/cdo-web/) — weather observations; historical finalized data cannot substitute for contemporaneous forecasts.

**Suitability caveat:** NWS API provides forecasts; EIA provides actual hourly grid operation data; forecast version history must be separately collected going forward.

## 2. Licensed commercial data, only after contract and approval
Historical forecast-vintage archives and regional power/gas forward executable quotes.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
None required; private forecasts must be separately permissioned.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
NWS issued and archived forecasts, EIA balancing authority hourly load and generation, power/gas futures settlements and basis. **Observation grain:** balancing authority × weather forecast issuance × lead hour. **Decision horizon:** forecast issuance is the earliest legal decision; never consume later realized weather or EIA actual load before release.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
