# SOURCES — Cyber-Outage Contingent Repo Funding Recovery Routes
## Tier 1: free/open official starting points
- **OFR working paper — Short Circuiting Short-Term Funding** (working paper, 2026-02-10): [official source](https://www.financialresearch.gov/working-papers/2026/02/10/short-circuiting-short-term-funding/). Empirical cyber outage simulation context, not a validation of this proposed controller.
- **OFR U.S. Repo Markets Data Release** (public data, current methodology page; checked 2026-11-20): [official source](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/). Cleared rates typically T+1; tri-party T+2; participant-level graph not public.
- **SEC Treasury Clearing Implementation** (regulatory source, checked 2026-11-20): [official source](https://www.sec.gov/featured-topics/treasury-clearing-implementation). Shows Dec 31 2026 eligible cash and June 30 2027 eligible repo dates; check exemptions.
**Data qualification:** Timestamped anonymized funding route uptime, fallback approvals, cutoff times, public OFR repo volumes/rates, synthetic outage schedules.
**Time qualification:** OFR cleared rate/volume normally T+1 and tri-party T+2, so use public series as lagged calibration only; route outage telemetry must be timestamped pre-decision.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- licensed intraday repo quote/settlement uptime panels
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- approved operational resilience exercise logs and funding relationships
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
- **OFR working paper — Short Circuiting Short-Term Funding** (working paper, 2026-02-10): [official source](https://www.financialresearch.gov/working-papers/2026/02/10/short-circuiting-short-term-funding/). Empirical cyber outage simulation context, not a validation of this proposed controller.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** Conditional multi-route recovery decreases funding shortfall and expected disruption cost more than an equal-cost static backup buffer.
- **Blocker:** required route × lender class × hourly outage scenario historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
