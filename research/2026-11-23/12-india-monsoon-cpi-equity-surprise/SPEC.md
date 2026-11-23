# SPEC — India Monsoon Surprise to Food CPI and Local Equity Pricing
**B17-12 / Global/domestic quant research; draft specification, approval pending.**

## Problem / use case
Calendar-average monsoon anomalies conceal crop-area heterogeneity and staggered CPI market dissemination.
**Decision:** Time/hedge exposures to monsoon-sensitive consumption and agriculture pricing after publicly available rainfall surprises.
**H1:** Rainfall surprises weighted by district crop patterns predict food-CPI subcomponents and cross-sectional consumer equity earnings revisions beyond national rainfall.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
Shock_t=Σ_d CropWeight_d*(Rain_d,t - Normal_d,t); ΔCPI_{t+h}=α+β*Shock_t+γ'Controls_t+ε
```
d district; crop weights fixed pre-season; h forecast horizon; normals from training vintage.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** IMD daily district rain, crop sowing weights, RBI CPI release, state-level harvest, NSE sector returns
**Decision and publication clock:** IMD publication timestamp and next-tradable-session; CPI only after official release, no revisions used retroactively.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Time/hedge exposures to monsoon-sensitive consumption and agriculture pricing after publicly available rainfall surprises. |
| REQ-002 | Baseline on matched opportunity set: All-India seasonal rainfall deviation plus autoregressive food CPI |
| REQ-003 | Research model: Hierarchical spatial distributed-lag regression + causal crop weighting |
| REQ-004 | Falsify using: CPI MAE, sector neutral-return IC, hit rate net costs, seasonal robustness |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Historical IMD OGD resources lag, crop mix revisions, rainfall not yield and policy interventions.
**Stop research if:** No incremental holdout inflation forecast or stock-return effect against rainfall benchmark.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $160k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$100k/$240k. Resulting 24m net ROI **-100.0% / -11.5% / 112.5% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
