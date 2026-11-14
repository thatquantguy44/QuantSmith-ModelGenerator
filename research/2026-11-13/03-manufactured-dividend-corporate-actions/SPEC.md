# SPEC — Manufactured-Dividend and Corporate-Action Loan Economics
**ID:** QMG-20261113-03 · **Status:** Draft; human approval required · **Category:** A · Securities finance · **Geography:** US and cross-listed global equities

## Problem and decision
Stock loans that cross ex-dividend, split, spin-off or merger windows can change manufactured payment, operational and tax-adjusted economics.
**Decision supported:** Determine whether a permitted loan extension, pre-event return or alternative allocation is economically superior without compromising beneficial-owner legal rights.

## H1 versus H0
**H1:** Event-time aware loan optimization removes avoidable payment/operational leakage relative to fee-only renewal rules while remaining faithful to tax/legal restrictions.
**H0:** A cost-inclusive Renew if lending fee remains positive and return only upon explicit mandatory recall. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
max_(a in eligible_actions) [fee(a)-manufactured_payment_adjustment(a)-corporate_action_cost(a)-recall_cost(a)-tax_adjustment(a)]
```
a is a legally permitted loan lifecycle action; each component is booked at the owner-specific event date and in consistent after-tax units.
**Capacity and eligibility:** Only owner-permitted loans and action windows; supply cannot be fabricated by the optimizer.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
Ex/record/pay dates; loan life; fee accrual; event elections; dividend amounts; owner tax flags and permitted return/recall rules. **Observation grain:** security × beneficial owner program × corporate-action event × decision timestamp. **Decision horizon:** event decisions before ex-date cutoff, using only announced corporate actions and approved tax interpretations then available.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Determine whether a permitted loan extension, pre-event return or alternative allocation is economically superior without compromising beneficial-owner legal rights. | Must |
| REQ-002 | Reproduce feasible benchmark: Renew if lending fee remains positive and return only upon explicit mandatory recall. | Must |
| REQ-003 | Implement candidate Rule-checked event economics and constrained loan life-cycle integer optimizer. only after benchmark | Must |
| REQ-004 | Report net program income, missed payment events, operational exceptions, unauthorized action count. and matched capacity/execution economics | Must |
| NFR-001 | Deterministic fixture replay, point-in-time lineage and seed/config pinning | Must |
| NFR-002 | Confidentiality, access/market eligibility, source licensing and manual review | Must |

## Acceptance criteria
| ID | Covers | Testable requirement |
|---|---|---|
| AC-001 | REQ-001,NFR-001 | Reject unavailable source vintages and impossible decision clocks |
| AC-002 | REQ-002 | Synthetic benchmark passes unit, cost and eligibility invariants |
| AC-003 | REQ-003 | Candidate uses same opportunities/cost rules; reproducible paired holdout |
| AC-004 | REQ-004 | Net economic metrics, intervals, sensitivity and capacity displayed |
| AC-005 | NFR-002 | Public output blocks private rows and unresolved authorization |

## Research economics
USD $150k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $45k–$310k over 24 months. Net ROI = (gross benefit − cost)/cost = **-70% to 107%**. NOT forecast or historical measurement. Economic lever: illustrative prevention of a small number of high-value event-payment exceptions and legal-allowable tax drag over two years.. Source availability: Public filings can anchor event timelines, but loan, tax and owner entitlement data are nonpublic.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Tax withholding, treaty benefits and manufactured-dividend treatment cannot be assumed from issuer-country information alone.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if post-cost incremental program income is nonpositive or event-aware policy increases mandatory-payment exceptions.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
