# SOURCES — SFTR Reporting Regime Drift and Public-Private Divergence Detector
## Tier 1: free/open official starting points
- **ESMA Securities Financing Transactions Reporting** (regulatory source, current reporting framework checked 2026-11-20): [official source](https://www.esma.europa.eu/data-reporting/sftr-reporting). Public reports are aggregates; transaction-level SFTR is permissioned.
- **ESMA trade-repository SFTR enforcement release** (regulatory enforcement, 2026-02-19): [official source](https://www.esma.europa.eu/press-news/esma-news/esma-sanctions-regis-tr-serious-breaches-organisational-obligations). Shows the economic importance of SFTR data quality; not specific model performance evidence.
**Data qualification:** ESMA reporting rules and publications, public aggregate exposures where available, historical methodology changes, synthetic backdated schema versions.
**Time qualification:** Use publication timestamps and repository versions, not reporting reference dates; detailed transaction data are supervisor-restricted.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- licensed vendor-assembled SFTR regulatory trend panels
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- approved trade repository access strictly subject to supervisory entitlements
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
No project-specific paper DOI was validated this run. Literature review remains an explicit research task; official portal references above are not journal article novelty proof.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** Joint change-point tests on volumes, missingness and reported collateral taxonomy identify synthetic or historical reporting breaks more reliably than absolute-value outlier rules.
- **Blocker:** required SFTR public aggregate series × jurisdiction × report vintage historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
