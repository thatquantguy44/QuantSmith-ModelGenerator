# Official-source and academic provenance inventory — checked 2026-11-13

The links below were verified as official provider pages or published paper records. Verify datasets, historical market vintages, usage rights and API access separately. Source publication timing is mandatory for every model.

## Source and paper catalog
- **sec** [SEC Treasury Clearing Implementation](https://www.sec.gov/featured-topics/treasury-clearing-implementation) — regulatory guidance, not a trade-level dataset.
- **dtcc** [DTCC US Treasury Clearing](https://www.dtcc.com/initiatives/ustclearing) — clearing model and published aggregate information, not participant margin files.
- **ofr** [OFR U.S. Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) — daily aggregated rates/volumes; cleared generally T+1, tri-party generally T+2; missing values possible.
- **pd** [New York Fed Primary Dealer Statistics](https://www.newyorkfed.org/markets/primarydealers) — published weekly primary dealer aggregate statistics; not a dealer inventory feed.
- **ofrpd** [OFR Primary Dealer Statistics data](https://www.financialresearch.gov/short-term-funding-monitor/datasets/nypd/) — public weekly dealer financing/fail aggregates; not specific participants.
- **sl** [New York Fed SOMA Securities Lending](https://www.newyorkfed.org/markets/domestic-market-operations/monetary-policy-implementation/securities-lending) — public operation auction results; not broad securities-lending fee market.
- **alfred** [FRED/ALFRED real-time vintage API documentation](https://fred.stlouisfed.org/docs/api/fred/realtime_period.html) — supports as-known-at historical macro vintages; series-specific release eligibility.
- **bis** [BIS global liquidity indicator portal](https://data.bis.org/topics/GLI) — quarterly cross-border credit metrics and methodological notes.
- **bisliq** [Brunnermeier–Pedersen, Market Liquidity and Funding Liquidity](https://doi.org/10.1093/rfs/hhn098) — peer-reviewed paper, conceptual context; not proof of proposed factor.
- **imf** [IMF International Investment Position](https://data.imf.org/en/datasets/IMF.STA%3AIIP) — international investment positions; observe reporting lag and revision schedules.
- **ecb** [ECB Euro Area Yield Curves](https://www.ecb.europa.eu/stats/financial_markets_and_interest_rates/euro_area_yield_curves/html/index.en.html) — published euro-area benchmark yield curves; not executable bond prices.
- **eia** [EIA Open Data/API](https://www.eia.gov/opendata/) — hourly electricity series and energy fundamentals; registration/terms may apply.
- **edgar** [SEC EDGAR APIs](https://www.sec.gov/search-filings/edgar-application-programming-interfaces) — public filings and XBRL; use public dissemination timestamps.
- **un** [UN Comtrade API documentation](https://comtradeplus.un.org/en/api-docs) — free preview limited to 500 rows; broader access and historical versions may require keys/premium.
- **cftc** [CFTC Commitments of Traders](https://www.cftc.gov/MarketReports/CommitmentsofTraders/index.htm) — positions as of Tuesday with public reporting later in the week.
- **finra** [FINRA TRACE overview](https://syndication.finra.org/content/what-trace-and-how-can-it-help-me) — public trades/aggregates; full historical bond-level feeds may be licensed.
- **noaa** [NOAA historical climate datasets](https://www.ncei.noaa.gov/cdo-web/) — weather observations; historical finalized data cannot substitute for contemporaneous forecasts.
- **nws** [US National Weather Service API](https://www.weather.gov/documentation/services-web-api) — public forecasts/alerts/observations; respect rate limits and issuance times.
- **oecd** [OECD SDMX API](https://www.oecd.org/en/data/insights/data-explainers/2024/09/api.html) — free economic data with revisions, publication lags and API terms.
- **msci** [MSCI index methodology](https://www.msci.com/indexes/index-resources/index-methodology) — public rules only; investable index return data and constituents may be licensed.
- **gabaix** [Gabaix–Maggiori, International Liquidity and Exchange Rate Dynamics](https://doi.org/10.1093/qje/qjv016) — peer-reviewed FX capital flow theory, not validation of proposed signal.
- **gu** [Gu–Kelly–Xiu, Empirical Asset Pricing via Machine Learning](https://doi.org/10.1093/rfs/hhaa009) — peer-reviewed ML asset pricing benchmark framework.
- **momentum** [Moskowitz–Ooi–Pedersen, Time Series Momentum](https://doi.org/10.1016/j.jfineco.2011.11.003) — published multi-asset benchmark, not evidence for specific new idea.
- **viral** [Haddad–Moreira–Muir, When Selling Becomes Viral](https://www.nber.org/papers/w27168) — working paper on market distress and fixed-income market dysfunction.

## Source-level truth policy
- SEC's December 31, 2026 eligible Treasury cash and June 30, 2027 repo compliance dates appear in the SEC implementation portal; eligibility/exemptions must be checked case by case.
- OFR publishes daily aggregate repo rates/volumes with documented lags and suppressed observations; treating report date as same-day tradable data is invalid.
- CFTC COT data are as-of Tuesday and usually published Friday; under no circumstances use Tuesday open interest before release.
- Published research links describe theory or historical empirical results. They do not validate any novel QMG production performance.
- Costs, ROI, capacity and idea rankings in this batch are authored **illustrative scenarios**, NOT externally sourced estimates or actual financial results.
- Additional credible papers may be cited after verification; lack of one is labeled an outstanding research task, not filled with fabricated references.
