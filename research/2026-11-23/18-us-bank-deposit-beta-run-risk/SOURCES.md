# SOURCES — US Bank Deposit Beta and Mark-to-Market Securities Run Risk
**Evidence state (Nov 23, 2026): Verified official public source *pages*; exact required series, licence, API accessibility and historical publication clock remain unresolved.** Context links are not proof of alpha, data availability, or paper novelty.

## Tier 1 — publicly accessible starting points
- **FDIC Bank Financial Reports** — Quarterly Call Reports with release delays, no real-time deposits. [Official source](https://www.fdic.gov/bank-financial-reports). Verified public page as of 2026-11-23; not verification of exact dataset access or licence.
- **FRED Data Portal** — US and global macro context; vintage-specific validation required. [Official source](https://fred.stlouisfed.org/). Verified public page as of 2026-11-23; not verification of exact dataset access or licence.

## Tier 2 — commercial/licensed
Bank funding rate panels and credit spread datasets. Obtain lawful entitlement, historical versions, executable bid/ask and permitted redistribution terms first. Never extract Cboe delayed quote tables programmatically where prohibited.

## Tier 3 — strictly permissioned / not in public GitHub
Authorized bank exposures, no private depositor/account data. No account positions, loan fees, counterparties, contracts or employer systems are included.

## Source-specific controls
Required panel: FDIC bank Call Reports, quarterly uninsured deposits, HTM/AFS loss fields, benchmark rates, bank equity CDS
Information gate: Quarter-end balances become usable only at the first public Call Report publication, not period end.
Potential release revisions: Quarterly revisions, mergers, bank survivorship and missing bank-specific deposit pricing.
A published source portal may carry a dataset whose latest revision would bias a historical test. Maintain immutable release and retrieval ledger with a quote/transaction observation clock.

## Literature and publication diligence
Medium-high financial stability research with clear accounting invariants. No individual academic paper has been confirmed as directly replicating this exact proposed experiment, so **no unverified DOI, author or paper performance claim is included**. Systematic literature review is a separate pending task.
