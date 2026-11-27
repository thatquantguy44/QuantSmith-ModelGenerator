# SOURCES — Biotech FDA Catalyst Probability versus Options Event Premium
**Evidence state (Nov 23, 2026): Verified official public source *pages*; exact required series, licence, API accessibility and historical publication clock remain unresolved.** Context links are not proof of alpha, data availability, or paper novelty.

## Tier 1 — publicly accessible starting points
- **openFDA Drugs@FDA** — Approval data; filing/decision event clocks need separate original documents. [Official source](https://open.fda.gov/data/drugsfda/). Verified public page as of 2026-11-23; not verification of exact dataset access or licence.
- **SEC EDGAR Data Access** — Issuer disclosure with explicit EDGAR acceptance/dissemination clock. [Official source](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data). Verified public page as of 2026-11-23; not verification of exact dataset access or licence.
- **Cboe Historical Options Market Statistics** — Historical volume, not historical executable option chain surfaces. [Official source](https://www.cboe.com/us/options/market_statistics/historical_data/). Verified public page as of 2026-11-23; not verification of exact dataset access or licence.

## Tier 2 — commercial/licensed
OptionMetrics/OPRA historical executable bid-ask quotes. Obtain lawful entitlement, historical versions, executable bid/ask and permitted redistribution terms first. Never extract Cboe delayed quote tables programmatically where prohibited.

## Tier 3 — strictly permissioned / not in public GitHub
Approved derivatives margin and short-option risk limits. No account positions, loan fees, counterparties, contracts or employer systems are included.

## Source-specific controls
Required panel: FDA event dates, approval histories, pre-event public filings, full options surfaces, equity halt and event-time trades
Information gate: No use of FDA outcome until public approval announcement; option quotes at last feasible pre-event time.
Potential release revisions: FDA database daily updates can lag original approval; sample selection, delistings and halted option quotes.
A published source portal may carry a dataset whose latest revision would bias a historical test. Maintain immutable release and retrieval ledger with a quote/transaction observation clock.

## Literature and publication diligence
High event-uncertainty methodology; historical quote availability is key. No individual academic paper has been confirmed as directly replicating this exact proposed experiment, so **no unverified DOI, author or paper performance claim is included**. Systematic literature review is a separate pending task.
