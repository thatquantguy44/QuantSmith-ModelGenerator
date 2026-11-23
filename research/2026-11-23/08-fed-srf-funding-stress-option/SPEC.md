# SPEC — Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal
**B17-08 / Securities finance; draft specification, approval pending.**

## Problem / use case
SRF usage can be distorted by auction mechanics and participants' idiosyncratic conditions, not just aggregate funding scarcity.
**Decision:** Monitor time-lagged facility usage and infer when broad repo funding stress warrants buffer review.
**H1:** Publication-aligned SRF utilization and awarded-rate dispersion improve next-session funding stress classification beyond SOFR-GC spread alone.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
P(Stress_{t+1}=1|F_t)=logit^{-1}(β0+β1*SRFAward_t+β2*RateDisp_t+β3*SOFRSpread_t)
```
Stress is pre-defined funding event; F_t contains only SRF summary published by decision time.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** Official SRF accepted/submitted quantities, summary rates, SOFR, OFR cleared/triparty repo aggregates
**Decision and publication clock:** Use posted operation result time and repo series 1-2-day publication lags; do not use same-day hidden participant-level bids.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Monitor time-lagged facility usage and infer when broad repo funding stress warrants buffer review. |
| REQ-002 | Baseline on matched opportunity set: SOFR-GC spread threshold with no SRF information |
| REQ-003 | Research model: Event-conditioned calibrated logistic hazard with lag-safe publication ledger |
| REQ-004 | Falsify using: Brier score, AUPRC, stress false alarm, lead-time, calibrated probability |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** SRF operational parameter changes, known policy regime shifts, lack of entity-level same-day data.
**Stop research if:** No holdout information gain after timing correction, or false positives overwhelm funding buffer costs.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $115k assumed total 24m development/data/maintenance cost; assumed launch in month 5; assumed annual gross outcome downside/base/upside $0k/$70k/$170k. Resulting 24m net ROI **-100.0% / -3.6% / 134.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
