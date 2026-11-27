# SPEC — CCP Member Default Position-Porting Time and Liquidity Optimization
**B17-09 / Securities finance; draft specification, approval pending.**

## Problem / use case
Porting eligible positions can fail due to margin deadlines, client permissions and receiving-member constraints even with adequate default-fund assets.
**Decision:** Choose contingent porting routes and liquidity reserves for a hypothetical clearing-member default.
**H1:** A capacity-constrained porting algorithm lowers simulated liquidation shortfall and time-to-restore relative to static member choice.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
min_{x_{ij}} Σ_{ij} x_{ij}*(PortDelay_{ij}+λ*MarginShortfall_{ij}) subject to Σ_j x_{ij}≤Position_i, K_j≥Σ_i x_{ij}
```
x_ij assigned position notional, K_j receiving-member capacity; only eligible clients/contracts included.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** Public CCP rulebooks; synthetic position/eligibility and margin profiles; simulated member outage
**Decision and publication clock:** Use rule versions effective on default scenario date, exclude assumptions from later CCP notices.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Choose contingent porting routes and liquidity reserves for a hypothetical clearing-member default. |
| REQ-002 | Baseline on matched opportunity set: Manual first-available eligible clearing member routing |
| REQ-003 | Research model: Multi-period mixed-integer stochastic porting/survival flow simulator |
| REQ-004 | Falsify using: Porting completion by deadline, unmet margin, loss given port failure, rerouting overhead |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Actual CCP porting legality and bilateral customer consents unknown, correlated failures may be unidentifiable.
**Stop research if:** No improvement in adverse default scenarios over conservative porting alternatives or reliance on forbidden client position data.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $210k assumed total 24m development/data/maintenance cost; assumed launch in month 10; assumed annual gross outcome downside/base/upside $0k/$95k/$330k. Resulting 24m net ROI **-100.0% / -47.2% / 83.3% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
