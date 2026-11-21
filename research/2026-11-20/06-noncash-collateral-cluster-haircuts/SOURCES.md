# SOURCES — Noncash Collateral Correlation-Cluster Haircut Controller
## Tier 1: free/open official starting points
- **OFR U.S. Repo Markets Data Release** (public data, current methodology page; checked 2026-11-20): [official source](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/). Cleared rates typically T+1; tri-party T+2; participant-level graph not public.
- **BIS/CPMI-IOSCO Principles for Financial Market Infrastructures** (regulatory standards, published 2012-04-16): [official source](https://www.bis.org/committees/cpmi/pfmi/overview). CCP/default-waterfall research context. Individual CCP loss allocation rules must be verified.
**Data qualification:** Approved collateral constituents, synthetic issuer cross-holdings, stressed factor returns, liquidation bid/ask, haircut and legal threshold.
**Time qualification:** Apply only return histories, prices, group linkages and issuer memberships known at the decision timestamp.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- licensed security-level collateral stress pricing and asset liquidity data
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- approved book collateral inventory and haircut agreements
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
No project-specific paper DOI was validated this run. Literature review remains an explicit research task; official portal references above are not journal article novelty proof.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** Cluster-aware chance constraints produce lower stressed shortfall than sector-flat haircuts at a matched average financing cost.
- **Blocker:** required collateral security × issuer cluster × loan exposure × as-of time historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
