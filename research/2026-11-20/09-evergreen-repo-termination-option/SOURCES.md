# SOURCES — Evergreen Repo Early-Termination Optionality Risk Budget
## Tier 1: free/open official starting points
- **OFR U.S. Repo Markets Data Release** (public data, current methodology page; checked 2026-11-20): [official source](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/). Cleared rates typically T+1; tri-party T+2; participant-level graph not public.
- **SEC Treasury Clearing Implementation** (regulatory source, checked 2026-11-20): [official source](https://www.sec.gov/featured-topics/treasury-clearing-implementation). Shows Dec 31 2026 eligible cash and June 30 2027 eligible repo dates; check exemptions.
**Data qualification:** Synthetic open-repo terms, public SOFR and OFR repo curve history, legally enforceable reset/termination terms and funding costs.
**Time qualification:** Public repo rates have release lags; exact contract termination rights must be known at contract initiation, not retrofitted.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- licensed executable repo term quotations and historical contract optionality research
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- approved agreement termination terms and repo open-contract events
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
No project-specific paper DOI was validated this run. Literature review remains an explicit research task; official portal references above are not journal article novelty proof.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** Notice-option-adjusted funding pricing reduces out-of-sample replacement-cost surprises versus duration-only term curve cost.
- **Blocker:** required contract × notice period × funding day × interest-rate state historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
