# SOURCES — Asia–US Cross-Listed ADR Opening Auction Information Transfer
## Tier 1: free/open official starting points
- **SEC developer resources and disclosure revisions** (public filings methodology, checked 2026-11-20): [official source](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data). Public filings can be corrected; store original accepted filing before any update.
- **SEC EDGAR API documentation** (public data API, updated 2025-04-08): [official source](https://www.sec.gov/search-filings/edgar-application-programming-interfaces). Companyfacts is not a complete source of issuer/customer segmentation or historical index membership.
**Data qualification:** Issuer depositary receipts ratios, local listings, public filings, FX quote timestamps, US ADR opening auctions, dividends and corporate action history.
**Time qualification:** Prevent local-price forward fill across sessions; ratio/corporate actions must be known at the US quote decision time.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- licensed US ADR and Asia local shares auction quotes, intraday FX, depositary ratio history
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- optional approved order-level fills for execution validation
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
No project-specific paper DOI was validated this run. Literature review remains an explicit research task; official portal references above are not journal article novelty proof.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** An asynchronous local-information estimator reduces US ADR opening-price execution error beyond last local close plus FX conversion.
- **Blocker:** required ADR × home-market session × US opening-auction timestamp historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
