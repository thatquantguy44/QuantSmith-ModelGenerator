# SOURCES — European CSDR Penalty-Aware Settlement Queue Prioritization
## Tier 1: free/open official starting points
- **ESMA CSDR Article 7 settlement-fail measures** (regulation, current rulebook checked 2026-11-20): [official source](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/csdr/article-7-measures-address-settlement-0). Daily cash penalties with exclusions; jurisdictional and effective-date reviews required.
- **ESMA cash penalty scope technical advice** (regulatory technical advice, 2025-06-26): [official source](https://www.esma.europa.eu/node/219934). Advice is not automatically operative law; capture adopted delegated acts separately.
**Data qualification:** Public ESMA CSDR framework, synthetic ISIN liquidity/penalty groups, settlement instruction cutoff, fail reason and amendment history.
**Time qualification:** Penalty exclusions and rules must reflect versions legally in force before each instruction decision; ESMA technical advice is not automatically operative law.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- licensed CSD settlement penalty rate and instruction history datasets
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- authorized ISIN-level fail reason, settlement queues and participant obligations
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
No project-specific paper DOI was validated this run. Literature review remains an explicit research task; official portal references above are not journal article novelty proof.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** A rule-aware queue policy lowers expected daily penalties and fail duration without worsening operational priority controls relative to FIFO.
- **Blocker:** required instruction × CSD × ISIN × intended settlement day × decision time historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
