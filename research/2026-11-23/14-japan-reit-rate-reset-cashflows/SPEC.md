# SPEC — Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization
**B17-14 / Global/domestic quant research; draft specification, approval pending.**

## Problem / use case
Nominal Japanese policy changes transmit unevenly to fixed versus floating J-REIT liabilities and rental pass-through.
**Decision:** Distinguish J-REIT rate-reset liability timing and property yield spreads rather than duration-only price sensitivity.
**H1:** Public debt-maturity reset exposure explains post-policy J-REIT return dispersion beyond NAV discount and generic duration beta.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
CashInterest_{i,t+h}=Σ_m Debt_{i,m}*(Coupon_{i,m}+ResetBeta_{i,m}*ΔRate_t); ΔAFFO_i≈-ΔCashInterest_i+RentPassThrough_i
```
i REIT, m debt tranche, ResetBeta contractual floating/reset sensitivity; AFFO cash flow.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** BOJ rate time series, J-REIT bond/debt disclosures, rent index, total returns and market-based NAV
**Decision and publication clock:** Use release/filing acceptance before BOJ event and timestamp debt disclosure versions.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Distinguish J-REIT rate-reset liability timing and property yield spreads rather than duration-only price sensitivity. |
| REQ-002 | Baseline on matched opportunity set: Market REIT index duration and price-to-NAV score |
| REQ-003 | Research model: Disclosure-derived maturity-wall factor with event-based hedged return regressions |
| REQ-004 | Falsify using: AFFO forecast error, sector-neutral return IC, liquidity-adjusted drawdown, event placebo |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Japanese disclosure translation/lease renewal timing and selective REIT survivorship.
**Stop research if:** No incremental post-rate-shift forecast after issuer fixed-effects and NAV-duration controls.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $150k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$85k/$235k. Resulting 24m net ROI **-100.0% / -19.7% / 121.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
