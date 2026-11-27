# SPEC — Chile–Peru Copper Royalty Shock to Sovereign and Mining Credit
**B17-15 / Global/domestic quant research; draft specification, approval pending.**

## Problem / use case
Copper price explains broad earnings but fiscal royalty changes can shift tax take and mine investment with different lags.
**Decision:** Hedge commodity-linked fiscal and issuer credit risk around public mining tax and royalty changes.
**H1:** Legislated effective marginal royalty changes predict issuer-versus-sovereign credit spread dispersion beyond copper returns.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
ΔSpread_{i,t+h}=β*Exposure_i*ΔRoyaltyRate_t+θ*ΔCopperPrice_t+γ'X_i,t+ε
```
Exposure_i public geographic mine revenue, ΔRoyaltyRate legislated effective tax not mere bill proposal.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** USGS production, government royalty statutes, country budgets, company annual filings, credit spreads and currency
**Decision and publication clock:** Policy event recognized at official publication/enactment time; annual USGS data only upon issuance.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Hedge commodity-linked fiscal and issuer credit risk around public mining tax and royalty changes. |
| REQ-002 | Baseline on matched opportunity set: Copper price beta plus sovereign spread changes |
| REQ-003 | Research model: Event study with cross-sectional mine exposure and staggered law timing |
| REQ-004 | Falsify using: Event abnormal spread, FX-adjusted carry, political timing placebo, credit risk attribution |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Anticipatory legislative pricing, issuer/sov high correlations, illiquid local bond prices.
**Stop research if:** No holdout effect after commodity beta and country shock controls or cannot identify legal effective date.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $170k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$95k/$260k. Resulting 24m net ROI **-100.0% / -25.5% / 103.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
