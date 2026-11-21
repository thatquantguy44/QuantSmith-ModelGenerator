# SOURCES — Japan FX Intervention Impact and Option-Skew Persistence
## Tier 1: free/open official starting points
- **Japan Ministry of Finance — 2026 Q3 intervention breakdown** (official data, 2026-11-09): [official source](https://www.mof.go.jp/english/policy/international_policy/reference/feio/quarter/2026_3Qe.html). July 30–Aug 3 2026 operations disclosed in later quarterly release; cannot use details before release.
- **Japan Ministry of Finance — FX intervention monthly release index** (official data, latest index checked 2026-11-20): [official source](https://www.mof.go.jp/english/policy/international_policy/reference/feio/monthly/index.html). Public monthly aggregate reports lag intervention days; do not make same-day predictions with ex-post labels.
**Data qualification:** MOF monthly/quarterly intervention releases and dates, spot FX, short-term rate differential, timestamped USDJPY options/forward data.
**Time qualification:** MOF 2026 Q3 intervention details published Nov 9, 2026; never use ex-post intervention date labels in same-day live-time signals.
Verified link = page exists as official context at 2026-11-20; it does not mean full economic data are free, exact historical vintages are accessible, or market quotes executable.

## Tier 2: commercial/vendor data, not committed
- licensed timestamped USDJPY spot/option vols and historical intervention newswire alerts
Before ingestion confirm terms, completeness, data dissemination lag, backfill policy, access fee, redistribution restriction and historical identifier mapping.

## Tier 3: permissioned/private research, NOT for public repo
- permissioned dealer FX order-flow data (optional; exclude from public repo)
No proprietary observations or credentials in this PR. Use approved environment and access policy only.

## Related verified literature and methodological links
No project-specific paper DOI was validated this run. Literature review remains an explicit research task; official portal references above are not journal article novelty proof.

## Evidence classification
- **Verified source context:** names/dated methodology on above official pages.
- **Hypothesis, not evidence:** A release-time-corrected intervention-event measure predicts conditional 1–20-day FX variance/skew adjustment beyond macro announcements and momentum.
- **Blocker:** required intervention disclosure event × FX option tenor × quote timestamp historical panel and price/cost availability not verified.
- **No made-up academic citation or performance claim.**
