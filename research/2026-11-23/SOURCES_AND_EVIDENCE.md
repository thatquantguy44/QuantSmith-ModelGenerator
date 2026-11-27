# Source ledger and methodological evidence — Batch 17
**Checked November 23, 2026.** These are verified public institutional webpages, not confirmations that all proposed data can be accessed freely or at required event granularity. Data snapshots, API rights, market prices and original academic papers still require due diligence.

| Source | Public starting point | Material limitation |
|---|---|---|
| mbsd | [DTCC FICC Mortgage-Backed Securities Division](https://www.dtcc.com/products-and-services/clearing-settlement-services/fixed-income-clearing-corporation-ficc/mortgage-backed-securities-division) | Market structure; not executable pool-level quote history |
| epn | [DTCC Electronic Pool Notification](https://www.dtcc.com/clearing-and-settlement-services/ficc-mbsd/epn) | Pool-delivery conventions; not transaction data |
| ofr | [OFR US Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) | Daily aggregate rates/volumes with specified publication delays |
| srf | [NY Fed Standing Repo Facility FAQ](https://www.newyorkfed.org/markets/repo-agreement-ops-faq-241218) | Operation procedures/result-publication rules; site may be revised |
| pd | [New York Fed Primary Dealer Statistics](https://www.newyorkfed.org/markets/primarydealers.html) | Weekly aggregated financing/positions/fails, delayed |
| bis | [BIS Basel III Monitoring Release, Sep 23 2026](https://www.bis.org/media-releases/20260923-basel-iii-risk-based-capital-and-leverage-ratios-are-stable-while-liquidity-indicators-show) | Aggregate Basel ratios; not bank-specific secured funding shadow costs |
| sec | [SEC EDGAR Data Access](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data) | Issuer disclosure with explicit EDGAR acceptance/dissemination clock |
| msrb | [MSRB EMMA Continuing Disclosures](https://www.msrb.org/Continuing-Disclosure) | Public issuer notices; bulk subscriptions may be licensed |
| fema | [FEMA National Risk Index public catalog](https://catalog.data.gov/dataset/national-risk-index-nri-data) | County/tract hazard baseline, version may be stale (2025) |
| india | [India Meteorological Department Rainfall Information](https://mausam.imd.gov.in/responsive/rainfallinformation.php) | Daily district/region rainfall; timestamp, archives and reuse need checks |
| indiaarchive | [India OGD Rainfall History](https://data.gov.in/catalog/rainfall-india) | Historical rain data; some resources end 2017 or revised 2021 |
| entsoe | [ENTSO-E Transparency Platform File Library Guide, Oct 9 2026](https://transparencyplatform.zendesk.com/hc/en-us/articles/35960137882129-File-Library-Guide) | European power datasets; registration, API rights and publication latency vary |
| boj | [Bank of Japan Time-Series Data Search](https://www.boj.or.jp/en/about/education/oshiete/statistics/h03.htm) | BOJ releases and time-series, asset granularity unconfirmed |
| usgs | [USGS Mineral Commodity Summaries 2026 dataset](https://www.usgs.gov/data/mineral-commodity-summaries-2026-data-release) | Annual country production statistics, CC0; not timely trades |
| fda | [openFDA Drugs@FDA](https://open.fda.gov/data/drugsfda/) | Approval data; filing/decision event clocks need separate original documents |
| imf | [IMF Sovereign Risk/DSA Publications](https://www.imf.org/en/publications/dsa/sovereign-risk-and-debt-sustainability-analysis-for-market-access-countries) | Public assessment methodology; publication time varies by country |
| worldbank | [World Bank Public DSA Country Repository](https://www.worldbank.org/en/programs/debt-toolkit/dsa) | Country public DSA lists; not executable sovereign prices |
| fdic | [FDIC Bank Financial Reports](https://www.fdic.gov/bank-financial-reports) | Quarterly Call Reports with release delays, no real-time deposits |
| jodi | [JODI-Oil World Database Downloads](https://www.jodidata.org/oil/database/data-downloads.aspx) | Free reported production/stocks; about monthly and subject to revisions |
| eia | [US EIA Public API](https://www.eia.gov/opendata/v1/) | Free energy time series with registration and series-specific publication |
| cboe | [Cboe Historical Options Market Statistics](https://www.cboe.com/us/options/market_statistics/historical_data/) | Historical volume, not historical executable option chain surfaces |
| cboelicense | [Cboe delayed options data restrictions](https://www.cboe.com/delayed_quotes/FREE/quote_table/) | Explicit automated-download restrictions; no scraping |
| fred | [FRED Data Portal](https://fred.stlouisfed.org/) | US and global macro context; vintage-specific validation required |

## Time-sensitive factual background
- DTCC FICC MBSD officially describes agency MBS post-trade clearing, TBA market and EPN delivery notification; this motivates idea #01 but does not reveal any executable rolls.
- OFR releases daily repo market data at 3pm with central cleared typically one-day and tri-party two-day lags, and suppressions for confidentiality. #08 cannot claim same-day market access.
- New York Fed SRF FAQ describes publication of summary operation quantities/rates and historical counterparty disclosure delay; no intraday proprietary award distribution inferred.
- EDGAR company-filings API has original submission and public acceptance dates. Daily indexes may be revised, so historical information is not equivalent to today's archive.
- EMMA offers free public municipal disclosures but paid/bulk access may have different licensing.
- India OGD historical rainfall catalog has stale subsets; IMD published current observational pages need historical availability validation.
- ENTSO-E File Library Guide updated Oct 9, 2026; access rights, time resolution and zone change timestamps vary.
- Drugs@FDA covers US drug regulatory records, but public daily snapshots may arrive later than an issuer press release or market halt.
- JODI monthly country oil stock/flow data are downloadable but have month-after reference lags and revisions.
- Cboe delayed options quote tables expressly prohibit programmatic extraction; idea #20 requires lawful licensed option market depth for empirical work.
- FEMA National Risk Index public catalog last updated July 2025 in the checked version and is a static hazard proxy, not realized insurance exit in 2026.
- USGS 2026 data release published September 18, 2026 and is descriptive annual production, not exact Chile/Peru royalty exposure.
- BIS Sep 23 2026 Basel monitoring is aggregate system data, NOT a bank's internal LCR or NSFR.
- FDIC Call Reports are quarterly and must use first public release timestamps.

## ROI equation, scenarios and risks
For each project: `C` = invented 24-month development + ongoing labour + approved data + cloud + maintenance cost in USD thousands. `AnnualB` = invented gross annual avoided loss or revenue equivalent, with downside 0, base and upside. `LaunchLag` = invented number of months before benefit begins. Net ROI = `(AnnualB × max(0,24-LaunchLag)/12 - C)/C`. Risk utility is not liquid cash. Funding, execution, capital, ownership and legal constraints must be estimated in independent real data analyses. Do not add benefit projections across projects; channels can overlap.
- 01 Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option: C=$180k; lag=6mo; annual gross downside/base/upside=$0k/$130k/$260k; 24m net ROI=-100.0% / 8.3% / 116.7% (downside/base/upside).
- 02 Corporate Bond Securities Lending from CDS Basis Hedge Demand: C=$150k; lag=7mo; annual gross downside/base/upside=$0k/$110k/$230k; 24m net ROI=-100.0% / 3.9% / 117.2% (downside/base/upside).
- 03 Repo Coupon and Principal Event Cash-Flow Netting Scheduler: C=$120k; lag=5mo; annual gross downside/base/upside=$0k/$95k/$190k; 24m net ROI=-100.0% / 25.3% / 150.7% (downside/base/upside).
- 04 Securities Loan Retroactive Rate Amendment Revenue Assurance: C=$105k; lag=4mo; annual gross downside/base/upside=$0k/$95k/$165k; 24m net ROI=-100.0% / 50.8% / 161.9% (downside/base/upside).
- 05 Borrow Scarcity Causal Effect on Equity Market-Maker Quoted Depth: C=$220k; lag=9mo; annual gross downside/base/upside=$0k/$120k/$310k; 24m net ROI=-100.0% / -31.8% / 76.1% (downside/base/upside).
- 06 Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes: C=$135k; lag=7mo; annual gross downside/base/upside=$0k/$80k/$225k; 24m net ROI=-100.0% / -16.0% / 136.1% (downside/base/upside).
- 07 Tri-Party Repo Margin Dispute Root-Cause and Evidence Classifier: C=$145k; lag=6mo; annual gross downside/base/upside=$0k/$110k/$205k; 24m net ROI=-100.0% / 13.8% / 112.1% (downside/base/upside).
- 08 Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal: C=$115k; lag=5mo; annual gross downside/base/upside=$0k/$70k/$170k; 24m net ROI=-100.0% / -3.6% / 134.1% (downside/base/upside).
- 09 CCP Member Default Position-Porting Time and Liquidity Optimization: C=$210k; lag=10mo; annual gross downside/base/upside=$0k/$95k/$330k; 24m net ROI=-100.0% / -47.2% / 83.3% (downside/base/upside).
- 10 Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral: C=$180k; lag=8mo; annual gross downside/base/upside=$0k/$120k/$280k; 24m net ROI=-100.0% / -11.1% / 107.4% (downside/base/upside).
- 11 US Municipal Credit Vulnerability to Local Insurance Withdrawal: C=$160k; lag=7mo; annual gross downside/base/upside=$0k/$100k/$260k; 24m net ROI=-100.0% / -11.5% / 130.2% (downside/base/upside).
- 12 India Monsoon Surprise to Food CPI and Local Equity Pricing: C=$160k; lag=7mo; annual gross downside/base/upside=$0k/$100k/$240k; 24m net ROI=-100.0% / -11.5% / 112.5% (downside/base/upside).
- 13 European Interconnector Congestion Power-Spread State Estimator: C=$220k; lag=9mo; annual gross downside/base/upside=$0k/$150k/$355k; 24m net ROI=-100.0% / -14.8% / 101.7% (downside/base/upside).
- 14 Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization: C=$150k; lag=7mo; annual gross downside/base/upside=$0k/$85k/$235k; 24m net ROI=-100.0% / -19.7% / 121.9% (downside/base/upside).
- 15 Chile–Peru Copper Royalty Shock to Sovereign and Mining Credit: C=$170k; lag=8mo; annual gross downside/base/upside=$0k/$95k/$260k; 24m net ROI=-100.0% / -25.5% / 103.9% (downside/base/upside).
- 16 Biotech FDA Catalyst Probability versus Options Event Premium: C=$195k; lag=9mo; annual gross downside/base/upside=$0k/$110k/$295k; 24m net ROI=-100.0% / -29.5% / 89.1% (downside/base/upside).
- 17 Sovereign DSA Rating Migration Event Pricing for Frontier Bonds: C=$175k; lag=9mo; annual gross downside/base/upside=$0k/$85k/$270k; 24m net ROI=-100.0% / -39.3% / 92.9% (downside/base/upside).
- 18 US Bank Deposit Beta and Mark-to-Market Securities Run Risk: C=$155k; lag=6mo; annual gross downside/base/upside=$0k/$120k/$245k; 24m net ROI=-100.0% / 16.1% / 137.1% (downside/base/upside).
- 19 OPEC Oil Balance Residuals and Refined Crack-Spread Transmission: C=$170k; lag=7mo; annual gross downside/base/upside=$0k/$115k/$280k; 24m net ROI=-100.0% / -4.2% / 133.3% (downside/base/upside).
- 20 Arbitrage-Free Equity Volatility Surface Repair Across Markets: C=$185k; lag=8mo; annual gross downside/base/upside=$0k/$105k/$265k; 24m net ROI=-100.0% / -24.3% / 91.0% (downside/base/upside).

## Academic source status
Primary official sources and institutional methodology are linked above. Specific academic paper DOIs were not independently verified on this run; paper-level replication and novelty review are **PENDING**, not represented by fabricated citations.
