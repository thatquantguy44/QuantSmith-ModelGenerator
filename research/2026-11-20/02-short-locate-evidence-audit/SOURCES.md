# SOURCES — Reg SHO Locate Evidence and Borrow-Capacity Audit Engine
## Tier 1: free/open official starting points
- **SEC Regulation SHO locate FAQ** (regulatory method, regulatory staff FAQ; checked 2026-11-20): [official source](https://www.sec.gov/rules-regulations/staff-guidance/trading-markets-frequently-asked-questions-8). Contains locate documentation, order-timing and exemption explanations; version applicable law before use.
**Data qualification:** Synthetic short-sale order events, documented locate timestamps, source identity, shares remaining, exemptions and post-trade recalls; later private desk records only if approved.
**Time qualification:** Locate documentation and quantity must be timestamped before short sale; revised records cannot retroactively authorize prior orders.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- audited market locate reference data where licensed
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- broker order/locate logs only in approved production compliance environment
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
No project-specific paper DOI was validated this run. Literature review remains an explicit research task; official portal references above are not journal article novelty proof.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** Event-sourced evidence reconstruction detects noncompliant or capacity-exhausted locates earlier than end-of-day exception review without excess false rejects.
- **Blocker:** required short-sale request × account × security × source × event timestamp historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
