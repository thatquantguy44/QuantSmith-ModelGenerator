# SOURCES — EU ETS Auction Supply Revision and Carbon Futures Carry
## Tier 1: free/open official starting points
- **European Commission — 2026/2027 EU ETS auction calendar** (official release, 2026-07-30): [official source](https://climate.ec.europa.eu/news-other-reads/news/revised-2026-and-2027-eu-ets1-auction-calendars-published-2026-07-30_en). Calendar revisions should be stored as public vintage and not forecast from final revised schedule.
- **European Commission — Union Registry** (official dataset portal, checked 2026-11-20; annual 2025 compliance data released 2026-10-05): [official source](https://climate.ec.europa.eu/areas-action/carbon-markets/eu-emissions-trading-system-eu-ets/union-registry_en). Annual emissions/compliance data may be delayed and are not intraday allowance inventories.
**Data qualification:** European Commission vintage auction calendars, Union Registry verified emissions/compliance, dated policy changes, EUA/power/gas contract prices.
**Time qualification:** 2027 auction schedule announced Jul 30 2026; 2025 compliance data public Oct 5 2026; only released data at as-of permitted.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- licensed EEX/ICE carbon futures curves and executable bid/ask
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- approved utility compliance balances and hedge exposures only in private setting
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
No project-specific paper DOI was validated this run. Literature review remains an explicit research task; official portal references above are not journal article novelty proof.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** Public-vintage auction-volume shocks improve calendar-spread/hedge-risk forecasts beyond front-month momentum and seasonal dummies.
- **Blocker:** required EU ETS auction calendar publication × allowance futures tenor × exchange quote timestamp historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
