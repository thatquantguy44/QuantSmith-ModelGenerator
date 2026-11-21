# SOURCES — Issuer Customer-Concentration Disclosure to Earnings Options Skew
## Tier 1: free/open official starting points
- **SEC EDGAR API documentation** (public data API, updated 2025-04-08): [official source](https://www.sec.gov/search-filings/edgar-application-programming-interfaces). Companyfacts is not a complete source of issuer/customer segmentation or historical index membership.
- **SEC developer resources and disclosure revisions** (public filings methodology, checked 2026-11-20): [official source](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data). Public filings can be corrected; store original accepted filing before any update.
**Data qualification:** SEC EDGAR original issuer filings, customer concentration disclosures, single-stock option surface, earnings calendar, liquidity and corporate actions.
**Time qualification:** Use SEC acceptance timestamps and first published disclosure, not retroactive tagged XBRL after amended filings.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- licensed historical options chain quotes, bid/ask, corporate actions and implied vols
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- none required initially; optional approved internal hedging fills
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
No project-specific paper DOI was validated this run. Literature review remains an explicit research task; official portal references above are not journal article novelty proof.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** Point-in-time EDGAR customer concentration disclosures explain forward options downside skew changes beyond leverage, size and event vol.
- **Blocker:** required issuer accepted filing × reported customer share × options quote timestamp historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
