# SPEC — Cleared Versus Tri-Party Repo Fragmentation Nowcast
**ID:** QMG-20261113-04 · **Status:** Draft; human approval required · **Category:** A · Securities finance · **Geography:** United States short-term funding markets

## Problem and decision
Aggregate secured funding can conceal diverging clearing venues, tenor demand and collateral composition, delaying recognition of venue-specific stress.
**Decision supported:** Adjust next-day funding risk overlays and desk liquidity buffers based on *publication-time* inter-venue segmentation rather than guessed live spreads.

## H1 versus H0
**H1:** A public-data fragmentation state predicts next-session tail moves in funding conditions beyond aggregate SOFR and repo volume.
**H0:** A cost-inclusive SOFR level change and aggregate funding volume z-score. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
F_t=Σ_v ω_v (r_v,t-r_ref,t)^2 + η*HHI(volume_v,t); predict P(stress_(t+1)|F_<=t, publication_lags)
```
v indexes funding venue/tenor/collateral categories; weights ω_v normalize liquidity; η calibrates volume concentration penalty.
**Capacity and eligibility:** An alert/risk-overlay product first; any later trade signal faces venue access, funding tenor and prices.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
OFR cleared and tri-party rate-volume series; collateral categories; SOFR; weekly dealer aggregate financing; release metadata. **Observation grain:** venue × collateral class × tenor × underlying observation date, plus public publication timestamp. **Decision horizon:** risk update only after OFR release; cleared repo T+1 and tri-party T+2 availability; never use same-day unpublished values.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Adjust next-day funding risk overlays and desk liquidity buffers based on *publication-time* inter-venue segmentation rather than guessed live spreads. | Must |
| REQ-002 | Reproduce feasible benchmark: SOFR level change and aggregate funding volume z-score. | Must |
| REQ-003 | Implement candidate State-space latent fragmentation index with lag-aware missingness. only after benchmark | Must |
| REQ-004 | Report next-session stress AUPRC, calibrated Brier score, false alarm rate, funding stress drawdown. and matched capacity/execution economics | Must |
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
USD $125k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $40k–$210k over 24 months. Net ROI = (gross benefit − cost)/cost = **-68% to 68%**. NOT forecast or historical measurement. Economic lever: scenario: avoid one or two large risk-buffer errors or reduce manual funding surveillance effort; no P&L is proven.. Source availability: OFR reports secured funding data with documented one- and two-day publication lags and confidentiality blanks.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Revised/missing suppressed OFR cells and cross-venue holiday timing can create lookahead and artificial divergences.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if lag-safe AUPRC does not exceed SOFR-only benchmark by 0.03 on an untouched crisis/quiet holdout.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
