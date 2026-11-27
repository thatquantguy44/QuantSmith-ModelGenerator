# Evidence ledger — 2026-11-27
Official URLs checked through public retrieval/search on this run; no datasets downloaded. Publication dates below refer to documents, not fresh market outcomes. Links are context/data entry points, not proof of historical release timestamps, access permissions, licenses, exact coverage or model performance.

- [OFR repo release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/): Rates/volumes by tenor and collateral; cleared usually one-day and tri-party two-day lag. Not security-level executable quotes.
- [DTCC rules and procedures](https://www.dtcc.com/legal/rules-and-procedures): Public rulebook index; effective historical rules, contractual applicability and transaction permissions require separate review.
- [Basel CRE22 historical version](https://www.bis.org/committees/bcbs/basel-framework/standard/cre/22/inforce/2022-01-01/published/2019-12-15): Reference for holding-period, currency-mismatch and netting concepts, not a current local-law determination.
- [FSB haircut framework, 7 September 2020](https://www.fsb.org/2020/09/regulatory-framework-for-haircuts-on-non-centrally-cleared-securities-financing-transactions-5/): Policy framework for certain non-centrally cleared SFTs; applicability and local implementation must be checked.
- [BIS Working Paper 1121, Margins, debt capacity, and systemic risk (7 September 2023)](https://www.bis.org/publications/working-paper-1121-margins-debt-capacity-and-systemic-risk): Background theory on margin and debt capacity; does not validate the candidate.
- [FINRA API documentation](https://developer.finra.org/docs): Consolidated short interest dataset; documentation specifies availability by 4:40 p.m. ET on publication date. Respect actual release clock.
- [ESMA EU SFT market overview (9 April 2024)](https://www.esma.europa.eu/press-news/esma-news/esma-publishes-first-overview-eu-securities-financing-transactions-markets): Aggregate market context, not access to confidential trade repository rows.
- [New York Fed reference rates](https://www.newyorkfed.org/markets/reference-rates): Published SOFR/TGCR/BGCR and compounded indexes; not deal quotes.
- [Bank of England SONIA methodology](https://www.bankofengland.co.uk/markets/sonia%20benchmark/sonia%20key%20features%20and%20policies): Distinguish rate observation and next-business-day index publication.
- [SEC EDGAR API documentation (6 June 2024)](https://www.sec.gov/search-filings/edgar-application-programming-interfaces): Public company submissions and XBRL API; track dissemination, accession, corrections and fair access.
- [SEC financial statement and notes data](https://www.sec.gov/data-research/sec-markets-data/financial-statement-notes-data-sets): Monthly bulk XBRL disclosure data; do not assume access on original period end or filing day.
- [INEGI IMMEX August 2026 release](https://en.www.inegi.org.mx/app/saladeprensa/noticia/11288): Monthly employment, hours and remuneration in IMMEX establishments; historical releases and regional coverage need audit.
- [SNB rates and FX data](https://data.snb.ch/de/topics/ziredev): Official FX/rates series; synchronized executable FX quotes and risk factors require additional sources.
- [ECB securities issues statistics](https://www.ecb.europa.eu/stats/financial_markets_and_interest_rates/securities/html/index.da.html): Issuer country/sector and stock-flow aggregates; does not prove individual covered-bond terms or spreads.
- [LME off-warrant stocks announcement, 17 March 2025](https://www.lme.com/en/News/Press-releases/2025/LME-provides-daily-insight-into-off-warrant-stocks): Announcement specifies delayed free T+3 and subscription T+1 access from April 2025; verify actual current delivery and licensing.
- [ONS stored-energy daily by subsystem](https://dados.ons.org.br/dataset/ear-diario-por-subsistema): Daily reservoir stored-energy dataset; ONS warns it may be revised after publication.
- [NBS real estate development January–April 2026 (19 May 2026)](https://www.stats.gov.cn/english/PressRelease/202605/t20260519_1963758.html): Official cumulative investment, sales, starts/completions and developer funding; preserve releases and comparable-basis changes.
- [CFPB 2025 HMDA release (31 March 2026)](https://www.consumerfinance.gov/about-us/newsroom/2025-hmda-data-on-mortgage-lending-now-available/): Annual privacy-modified loan applications, not live rate-lock timestamps.
- [Freddie Mac PMMS](https://www.freddiemac.com/pmms): Weekly mortgage application rate survey; not lock-level prices or outcomes.
- [OECD Pension Markets in Focus 2025 (12 November 2025)](https://www.oecd.org/en/publications/pension-markets-in-focus-2025_b095d0a0-en.html): Annual asset allocation and flows; not institution-specific trade dates or live flows.

BIS Working Paper 1121 is verified background literature only. Additional academic DOI validation and systematic literature novelty are BLOCKED pending targeted review. ROI calculations use stated hypothetical project budget, annual benefit and delay; one cannot add benefits across overlapping opportunity sets. No data redistribution.

- 01: dtcc,ofr; licensed need: security-level executable financing costs and reference data; private need: approved collateral lots and eligibility agreements.
- 02: fsb,bis,basel; licensed need: licensed security prices, liquidation depth and haircut history; private need: approved haircut policy and closeout event data.
- 03: esma,finra; licensed need: licensed fee/availability snapshots; private need: approved signed commitments and draw histories.
- 04: nyfed,sonia; licensed need: licensed forward curves and funding quotes; private need: approved executed convention text and cash accrual ledger.
- 05: finra,esma; licensed need: licensed historical lendable supply and loan balances; private need: approved anonymized lending-event observations for state labels.
- 06: dtcc,esma; licensed need: settlement security master and rule/fee data; private need: approved obligation snapshots and partial-settlement terms.
- 07: ofr,esma; licensed need: independent licensed repo marks and executable reference quotes; private need: approved anonymized RFQ event records and consented experiment protocol.
- 08: dtcc,basel; licensed need: licensed pricing/risk engine inputs; private need: approved margin calculator and netting-set snapshots.
- 09: basel,snb,fsb; licensed need: licensed synchronized FX forwards and collateral price histories; private need: authorized collateral exposures and hedge policy.
- 10: ofr,nyfed,esma; licensed need: licensed repo term and market stress history; private need: approved contractual maturity and rollover records.
- 11: sec,notes; licensed need: point-in-time prices, split/delisting returns and issuance vendor; private need: approved portfolio exposure for risk translation.
- 12: mex,sec; licensed need: licensed Mexican equity prices and company geographic exposures; private need: approved portfolio sector weights.
- 13: snb,oecd; licensed need: licensed FX forward curves and total return indexes; private need: approved portfolio beta and currency hedge limits.
- 14: ecb,sec; licensed need: licensed individual bond terms, curves, ratings and issue spreads; private need: approved issuer watchlist and exposure limits.
- 15: sec,notes; licensed need: licensed split-adjusted/delisted returns, estimates and corporate actions; private need: approved research analyst labels only.
- 16: lme; licensed need: licensed warehouse/price history and executable futures bid/ask; private need: approved risk and position capacity.
- 17: ons; licensed need: licensed settlement prices and Brazilian company exposures; private need: approved utility contracts or risk exposures.
- 18: china,sec; licensed need: licensed Chinese/Asian bond prices, developer reports and corporate actions; private need: approved credit exposure and escrow legal review.
- 19: hmda,pmms; licensed need: licensed TBA/rates quotes and mortgage pipeline benchmarks; private need: approved de-identified lock-level history, no raw applicant data publication.
- 20: oecd; licensed need: licensed index returns and execution cost curves; private need: approved plan policy and cashflow schedules.
