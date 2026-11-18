# Specification — Treasury Futures Delivery Inventory Reservation

**QMG-20261116-04 · A — Securities finance · research design, empirical state BLOCKED.**

## Decision and hypothesis

Reserve eligible inventory for an existing futures short versus lending it, charging the marginal delivery-option opportunity cost. A delivery-option reserve beats a fixed percentage holdback by at least 2 bps of annualized affected inventory value, after replacement, lending and hedge costs.

```text
max_l E[sum_i fee_i*l_i*dt + V_delivery(I-l,F,P)] - replacement(l); 0<=l_i<=I_i, sum_i d_i=N_contracts, face_per_contract*d_i<=I_i-l_i, d_i integer>=0, stress_DV01<=limit
```

I and l are face inventory and lent quantity; CF conversion factors enter invoice_i=face_per_contract*(CF_i*F+AI_i)/100; d_i integer delivery contracts assigned to CUSIP i; N_contracts existing delivery obligation; F futures price per 100 face; AI accrued interest per 100 face; P cash prices; V_delivery optimal invoice less cash opportunity value under delivery rules. Fee carry uses the actual marked value and year fraction; inventory eligibility and delivery date are hard constraints.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-04-REQ-01 | Ingest CUSIP x futures contract x observation timestamp | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-04-REQ-02 | Build invoice value, basket eligibility and marginal delivery option shadow cost | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-04-REQ-03 | Implement baseline: Hold back 10% of eligible basket inventory and allocate remaining loans using current fees. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-04-REQ-04 | Fit/solve Scenario dynamic programming for marginal delivery-option value | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-04-REQ-05 | Evaluate net lending revenue plus delivery economics for a fixed pre-existing futures obligation | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-04-REQ-06 | Produce lendable face limits and delivery-feasibility certificate | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-04-NFR-01 | Contract units, invoice rounding and delivery rules must be versioned and independently reconciled before optimization. |
| QMG-20261116-04-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-04-AC-01 | GO if >=2 annualized bps saving over fixed holdback across >=8 delivery cycles, no missed delivery and positive benefit at twice observed transaction costs. STOP if gains depend on hindsight cheapest-to-deliver identity. |
| QMG-20261116-04-AC-02 | Freeze the basket to a single security: option-selection value must vanish; change conversion factor units and require invoice identity failure rather than silent rescaling. |
| QMG-20261116-04-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Published conversion factors and contract rules; futures and cash bid/ask, repo fees, loan terms, delivery notices and hedge positions. Public basket tables are insufficient for option valuation. Clock: Reserve at 15:00 America/Chicago using quotes available by 14:55 and current contract basket version; subsequent delivery notices are outcomes, never predictive features. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Endogenous cheapest-to-deliver switches, delivery timing rules and fee cancellation terms matter; mark-to-model delivery value is not realized cash profit. Illustrative $250m affected deliverable inventory. Limited by futures obligation size and deliverable-lot depth; do not take a new directional basis trade merely to generate lending revenue. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: High: interaction of delivery options and lending availability; empirical claim requires licensed synchronized markets.
