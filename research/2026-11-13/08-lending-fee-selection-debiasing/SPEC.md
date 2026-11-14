# SPEC — Securities-Lending Fee Observability & Selection-Bias Corrector
**ID:** QMG-20261113-08 · **Status:** Draft; human approval required · **Category:** A · Securities finance · **Geography:** US/global securities lending benchmarks

## Problem and decision
Published securities-loan fee samples cover executed and contributed loans unevenly; rare specials and failed locates can be missing non-randomly.
**Decision supported:** Publish uncertainty-aware fee benchmarks and abstain from quote-setting when selected sample coverage is inadequate.

## H1 versus H0
**H1:** Explicit observability weighting and partial identification shrink apparent fee benchmark error versus sample-weighted means on contributor holdouts.
**H0:** A cost-inclusive Daily equally weighted or outstanding-value-weighted observed market fees. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
mu_hat = Σ_i w_i*y_i/Σ_i w_i; w_i=1/P(observed_i|X_i); report sensitivity to unidentified selection
```
y_i is observed fee; X_i observable security/liquidity/context; propensity weights are estimated from an externally validated sample frame.
**Capacity and eligibility:** Primarily an internal benchmark/data product; no automatic quoting when source coverage or liquidity is inadequate.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
Contributed executed fee samples; public security volume/short-interest proxies; locate response metadata; source coverage and revisions. **Observation grain:** security × lending day × vendor/contributor population. **Decision horizon:** benchmark at next published cutoff; never use end-of-day contributions before receipt.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Publish uncertainty-aware fee benchmarks and abstain from quote-setting when selected sample coverage is inadequate. | Must |
| REQ-002 | Reproduce feasible benchmark: Daily equally weighted or outstanding-value-weighted observed market fees. | Must |
| REQ-003 | Implement candidate Doubly robust weighting with overlap and selection-sensitivity intervals. only after benchmark | Must |
| REQ-004 | Report cross-contributor benchmark error, interval coverage, abstention, quote drift, market breadth coverage. and matched capacity/execution economics | Must |
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
USD $120k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $45k–$230k over 24 months. Net ROI = (gross benefit − cost)/cost = **-62% to 92%**. NOT forecast or historical measurement. Economic lever: scenario: avoid mispriced lending quotes on a small subset of specials; savings not inferable from the public sources alone.. Source availability: Public security market data can inform context, but no complete free securities-loan execution tape is assumed.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Missing-not-at-random selection cannot be identified from executed loans alone; confidence intervals can be falsely narrow.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if cross-contributor MAE reduction <10% or intervals under-cover known withheld contributions.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
