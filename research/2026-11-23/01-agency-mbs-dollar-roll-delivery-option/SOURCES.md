# SOURCES — Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option
**Evidence state (Nov 23, 2026): Verified official public source *pages*; exact required series, licence, API accessibility and historical publication clock remain unresolved.** Context links are not proof of alpha, data availability, or paper novelty.

## Tier 1 — publicly accessible starting points
- **DTCC FICC Mortgage-Backed Securities Division** — Market structure; not executable pool-level quote history. [Official source](https://www.dtcc.com/products-and-services/clearing-settlement-services/fixed-income-clearing-corporation-ficc/mortgage-backed-securities-division). Verified public page as of 2026-11-23; not verification of exact dataset access or licence.
- **DTCC Electronic Pool Notification** — Pool-delivery conventions; not transaction data. [Official source](https://www.dtcc.com/clearing-and-settlement-services/ficc-mbsd/epn). Verified public page as of 2026-11-23; not verification of exact dataset access or licence.

## Tier 2 — commercial/licensed
Executable TBA rolls, specified-pool prices, MBS prepayment factors. Obtain lawful entitlement, historical versions, executable bid/ask and permitted redistribution terms first. Never extract Cboe delayed quote tables programmatically where prohibited.

## Tier 3 — strictly permissioned / not in public GitHub
Approved pool inventory, counterparties and EPN allocations; never commit actual records. No account positions, loan fees, counterparties, contracts or employer systems are included.

## Source-specific controls
Required panel: TBA front/back prices, pools, payups, coupon schedules, specified-pool risk, MBSD netting, EPN eligibility and execution costs
Information gate: Decision at pre-roll executable quote; EPN pool assignment becomes known later and must not leak into earlier signals.
Potential release revisions: Pool price selection, payup optionality, actual pool availability and post-trade EPN leakage.
A published source portal may carry a dataset whose latest revision would bias a historical test. Maintain immutable release and retrieval ledger with a quote/transaction observation clock.

## Literature and publication diligence
High for delivery-option identification; economic calibration requires licensed pool execution data. No individual academic paper has been confirmed as directly replicating this exact proposed experiment, so **no unverified DOI, author or paper performance claim is included**. Systematic literature review is a separate pending task.
