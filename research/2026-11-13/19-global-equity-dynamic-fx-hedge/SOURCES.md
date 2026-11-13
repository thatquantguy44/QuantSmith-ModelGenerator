# SOURCES — Dynamic Currency-Hedge and Rebalancing Tax for Global Equity
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [MSCI index methodology](https://www.msci.com/indexes/index-resources/index-methodology) — public rules only; investable index return data and constituents may be licensed.
- [ECB Euro Area Yield Curves](https://www.ecb.europa.eu/stats/financial_markets_and_interest_rates/euro_area_yield_curves/html/index.en.html) — published euro-area benchmark yield curves; not executable bond prices.
- [Gabaix–Maggiori, International Liquidity and Exchange Rate Dynamics](https://doi.org/10.1093/qje/qjv016) — peer-reviewed FX capital flow theory, not validation of proposed signal.
- [BIS global liquidity indicator portal](https://data.bis.org/topics/GLI) — quarterly cross-border credit metrics and methodological notes.

**Suitability caveat:** MSCI publishes methodology, not unrestricted total return/constituent history; FX and rates data may have licensing restrictions.

## 2. Licensed commercial data, only after contract and approval
Licensed global total return index histories, executable FX forwards and capital-control calendars.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
No required private data.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
Country index total returns, currency spot/forward curves, FX liquidity, investability restrictions and funding rates. **Observation grain:** country equity market × FX forward tenor × monthly rebalance date. **Decision horizon:** rebalance at scheduled month-end using prior-close prices and then-available forward quotes.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
