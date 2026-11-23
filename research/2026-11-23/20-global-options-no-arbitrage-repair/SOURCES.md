# SOURCES — Arbitrage-Free Equity Volatility Surface Repair Across Markets
**Evidence state (Nov 23, 2026): Verified official public source *pages*; exact required series, licence, API accessibility and historical publication clock remain unresolved.** Context links are not proof of alpha, data availability, or paper novelty.

## Tier 1 — publicly accessible starting points
- **Cboe Historical Options Market Statistics** — Historical volume, not historical executable option chain surfaces. [Official source](https://www.cboe.com/us/options/market_statistics/historical_data/). Verified public page as of 2026-11-23; not verification of exact dataset access or licence.
- **Cboe delayed options data restrictions** — Explicit automated-download restrictions; no scraping. [Official source](https://www.cboe.com/delayed_quotes/FREE/quote_table/). Verified public page as of 2026-11-23; not verification of exact dataset access or licence.

## Tier 2 — commercial/licensed
Licensed cross-exchange historical option chains, forward curves and bid-ask depths. Obtain lawful entitlement, historical versions, executable bid/ask and permitted redistribution terms first. Never extract Cboe delayed quote tables programmatically where prohibited.

## Tier 3 — strictly permissioned / not in public GitHub
Approved option market-making Greeks and trade limits. No account positions, loan fees, counterparties, contracts or employer systems are included.

## Source-specific controls
Required panel: Time-synchronized option bid/ask, underlying forwards, dividends, exchange calendars, corporate action adjustments
Information gate: Quote timestamp aligned to each exchange session; repair uses no quotes from future or closed-market snapshots.
Potential release revisions: American vs European option styles, dividend marks, early exercise, restricted historical quote rights.
A published source portal may carry a dataset whose latest revision would bias a historical test. Maintain immutable release and retrieval ledger with a quote/transaction observation clock.

## Literature and publication diligence
High applied numerical finance with auditable negative tests, but licensed history required. No individual academic paper has been confirmed as directly replicating this exact proposed experiment, so **no unverified DOI, author or paper performance claim is included**. Systematic literature review is a separate pending task.
