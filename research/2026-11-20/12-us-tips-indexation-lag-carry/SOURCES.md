# SOURCES — US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface
## Tier 1: free/open official starting points
- **U.S. Treasury Fiscal Data — TIPS and CPI** (public data, last updated 2026-11-10): [official source](https://fiscaldata.treasury.gov/datasets/tips-cpi-data/). Monthly and daily ratios; preserve publication time and revision flags; securities prices require separate data.
- **SEC EDGAR API documentation** (public data API, updated 2025-04-08): [official source](https://www.sec.gov/search-filings/edgar-application-programming-interfaces). Companyfacts is not a complete source of issuer/customer segmentation or historical index membership.
**Data qualification:** Treasury official daily TIPS index ratios/CPI, vintage BLS CPI, nominal/TIPS quotes, issue terms, accrued interest.
**Time qualification:** Daily index ratios can be forecast only from already published reference CPI; preserve first release and later corrections.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- licensed nominal/TIPS bond transaction and inflation swap market data
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- optional approved portfolio duration and executed bond quotes
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
No project-specific paper DOI was validated this run. Literature review remains an explicit research task; official portal references above are not journal article novelty proof.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** A vintage-consistent carry decomposition improves matched-duration real-vs-nominal excess-return hedging net of liquidity/rollover costs.
- **Blocker:** required TIPS CUSIP × CPI/index-ratio effective date × decision timestamp historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
