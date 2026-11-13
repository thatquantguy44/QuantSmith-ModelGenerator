# SOURCES — CFTC Positioning Concentration and Commodity Curve Convexity
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [CFTC Commitments of Traders](https://www.cftc.gov/MarketReports/CommitmentsofTraders/index.htm) — positions as of Tuesday with public reporting later in the week.
- [EIA Open Data/API](https://www.eia.gov/opendata/) — hourly electricity series and energy fundamentals; registration/terms may apply.
- [Moskowitz–Ooi–Pedersen, Time Series Momentum](https://doi.org/10.1016/j.jfineco.2011.11.003) — published multi-asset benchmark, not evidence for specific new idea.

**Suitability caveat:** CFTC public positioning has Tuesday reference dates and Friday releases; curve prices may be delayed/paid.

## 2. Licensed commercial data, only after contract and approval
Executable futures historical bid/ask term structure and expiry calendars.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
None essential.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
CFTC Disaggregated COT futures positions, futures contracts prices/rolls, EIA physical inventories where applicable. **Observation grain:** CFTC contract market × Tuesday reference position × Friday public release, then weekly trade clock. **Decision horizon:** earliest action is CFTC publication/next executable session; no use of Tuesday positions on Tuesday.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
