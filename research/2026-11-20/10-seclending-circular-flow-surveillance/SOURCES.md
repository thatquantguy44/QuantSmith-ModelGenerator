# SOURCES — Securities-Lending Circular Flow Surveillance via Temporal Graphs
## Tier 1: free/open official starting points
- **ESMA Securities Financing Transactions Reporting** (regulatory source, current reporting framework checked 2026-11-20): [official source](https://www.esma.europa.eu/data-reporting/sftr-reporting). Public reports are aggregates; transaction-level SFTR is permissioned.
- **SEC Regulation SHO locate FAQ** (regulatory method, regulatory staff FAQ; checked 2026-11-20): [official source](https://www.sec.gov/rules-regulations/staff-guidance/trading-markets-frequently-asked-questions-8). Contains locate documentation, order-timing and exemption explanations; version applicable law before use.
**Data qualification:** Synthetic multi-party loan/return event graph, matched collateral movement, legitimate transfer controls, anonymized case annotations if permitted.
**Time qualification:** Create graph only from recorded transfers visible before alert time; disallow knowledge of subsequent investigation outcomes in features.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- licensed anonymized SFT operational aggregate benchmark where lawful
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- restricted counterparty event flows available only in approved surveillance systems
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
No project-specific paper DOI was validated this run. Literature review remains an explicit research task; official portal references above are not journal article novelty proof.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** Causal temporal-motif alerts improve precision at fixed review capacity over pairwise round-trip thresholds in seeded synthetic cases.
- **Blocker:** required synthetic securities loan transfer edge × security × event timestamp historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
