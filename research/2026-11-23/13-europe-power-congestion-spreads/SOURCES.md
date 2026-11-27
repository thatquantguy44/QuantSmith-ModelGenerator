# SOURCES — European Interconnector Congestion Power-Spread State Estimator
**Evidence state (Nov 23, 2026): Verified official public source *pages*; exact required series, licence, API accessibility and historical publication clock remain unresolved.** Context links are not proof of alpha, data availability, or paper novelty.

## Tier 1 — publicly accessible starting points
- **ENTSO-E Transparency Platform File Library Guide, Oct 9 2026** — European power datasets; registration, API rights and publication latency vary. [Official source](https://transparencyplatform.zendesk.com/hc/en-us/articles/35960137882129-File-Library-Guide). Verified public page as of 2026-11-23; not verification of exact dataset access or licence.
- **US EIA Public API** — Free energy time series with registration and series-specific publication. [Official source](https://www.eia.gov/opendata/v1/). Verified public page as of 2026-11-23; not verification of exact dataset access or licence.

## Tier 2 — commercial/licensed
Executable EPEX/ICE forward curves and interconnector rights prices. Obtain lawful entitlement, historical versions, executable bid/ask and permitted redistribution terms first. Never extract Cboe delayed quote tables programmatically where prohibited.

## Tier 3 — strictly permissioned / not in public GitHub
Permissioned utility node positions and hedging restrictions. No account positions, loan fees, counterparties, contracts or employer systems are included.

## Source-specific controls
Required panel: ENTSO-E day-ahead prices, transfer capacities, interconnector outages, wind/load forecasts and contract liquidity
Information gate: Only ENTSO-E forecasts published before day-ahead bidding deadline; actual flows/prices are evaluation targets.
Potential release revisions: Cross-zone transmission rights and operational capacities not freely tradable; timestamps and price revisions.
A published source portal may carry a dataset whose latest revision would bias a historical test. Maintain immutable release and retrieval ledger with a quote/transaction observation clock.

## Literature and publication diligence
Very high physics/market design; data-rights and operational access are gating. No individual academic paper has been confirmed as directly replicating this exact proposed experiment, so **no unverified DOI, author or paper performance claim is included**. Systematic literature review is a separate pending task.
