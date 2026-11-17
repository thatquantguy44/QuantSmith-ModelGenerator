# Specification — Securities-Loan Dust-Lot Consolidation

**QMG-20261116-10 · A — Securities finance · research design, empirical state BLOCKED.**

## Decision and hypothesis

Consolidate or close eligible small lots within the same owner/borrower/legal permissions while preserving economic exposure and service constraints. Integer cost-aware lot consolidation cuts recurring servicing expense by at least 20% relative to pro-rata allocation without reducing net lending revenue by more than 1%.

```text
max_(x,z) sum_(o,b,i) fee_obi*x_obi*dt - k_obi*z_obi - move_cost; lot_i*z_obi<=x_obi<=M_obi*z_obi, sum_b x_obi<=I_oi, sum_o x_obi=D_bi, z binary
```

o owner, b borrower, i security; x loan quantity; z active lot; fee net per-unit revenue; k recurring ticket cost; lot minimum economic/settlement size; I inventory; D approved demand; M individual legal capacity. Existing owner allocations may be immutable unless consent permits changes.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-10-REQ-01 | Ingest owner x borrower x security loan lot x service day | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-10-REQ-02 | Build fixed servicing charge, permitted owner-lot map and movement-cost matrix | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-10-REQ-03 | Implement baseline: Pro-rata eligible allocation across owners, subject to existing concentration caps. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-10-REQ-04 | Fit/solve Fixed-charge transportation MILP | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-10-REQ-05 | Evaluate active-ticket count and net servicing-adjusted margin | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-10-REQ-06 | Produce consolidation suggestions with per-owner exposure/revenue reconciliation | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-10-NFR-01 | Deterministic tie-breaking and original-book fallback on infeasibility; quantity and owner revenue reconcile exactly to declared permitted changes. |
| QMG-20261116-10-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-10-AC-01 | GO if >=20% servicing-cost saving and <=1% net revenue loss, zero owner-rights violations and payback within 12 months on measured cost inputs. STOP if gains disappear after movement fees or permitted allocations are fixed. |
| QMG-20261116-10-AC-02 | Set per-ticket cost to zero: consolidation must not invent savings; introduce an owner-specific nontransferability flag and verify its lot remains untouched. |
| QMG-20261116-10-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Synthetic owner/borrower inventories, approved minimum lots, source shares, per-ticket servicing fees, loan quantities, movement cost and owner allocation rules. No real owner or borrower data are committed. Clock: Solve after confirmed end-of-day books and before next-day instruction cutoff; only booked demand and valid consent known at solve time enter. Settled movements are later outcomes. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Tax lots, revenue attribution, beneficial-owner fairness and contract permissions can prohibit economically appealing consolidation. Unit-cost assumptions often dominate the result. Illustrative 50,000 serviced lots per year; no market ADV capacity claim. Benefits limited by actual removable lots and movement/consent cost, not gross notional. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: Medium: fixed-charge inventory allocation with fair attribution; production engineering likely more valuable than model novelty.
