# SOURCES — ETF Creation/Redemption Basket Shock to Stock-Loan Supply
## Tier 1: free/open official starting points
- **SEC EDGAR API documentation** (public data API, updated 2025-04-08): [official source](https://www.sec.gov/search-filings/edgar-application-programming-interfaces). Companyfacts is not a complete source of issuer/customer segmentation or historical index membership.
- **SEC developer resources and disclosure revisions** (public filings methodology, checked 2026-11-20): [official source](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data). Public filings can be corrected; store original accepted filing before any update.
**Data qualification:** ETF disclosed holdings and creation units, public filings, official membership events, licensed AP basket/flows and loan availability for later study.
**Time qualification:** Only baskets available to a decision-maker before ETF order cutoff may be used; end-of-day holding reports are not morning baskets.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- licensed NSCC/ETF basket files, creation/redemption flows and securities lending availability
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- permissioned lendable supply, client inventory rules and loan booking logs
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
No project-specific paper DOI was validated this run. Literature review remains an explicit research task; official portal references above are not journal article novelty proof.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** Point-in-time basket-flow measures predict incremental short-horizon available-to-lend changes beyond conventional index membership and short-interest proxies.
- **Blocker:** required ETF × constituent × creation/redemption day × publication time historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
