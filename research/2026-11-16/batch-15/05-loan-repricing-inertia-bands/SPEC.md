# Specification — Stock-Loan Repricing Bands with Relationship Friction

**QMG-20261116-05 · A — Securities finance · research design, empirical state BLOCKED.**

## Decision and hypothesis

Choose a fee-change threshold and batching cadence for existing loans rather than repricing every observed basis-point move. A two-sided repricing band increases net relationship-adjusted revenue by at least 5% versus daily benchmark matching without reducing risk-adjusted balances by more than 2%.

```text
V(f,m)=max{carry(f,m)+E[V(f,m_next)], max_(f_new)[carry(f_new,m)-K-C_exit(f_new,f,m)+E[V(f_new,m_next)]]}; f_min<=f_new<=f_max, messages_day<=M
```

f is current annualized loan fee; m public/licensed market state; K fixed negotiation/processing cost; C_exit expected lost margin from borrower response; M approved message cap. Carry is fee times marked loan notional times elapsed year fraction, less source costs.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-05-REQ-01 | Ingest loan x repricing proposal/response event | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-05-REQ-02 | Build fee gap, duration in band, response propensity and net processing cost | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-05-REQ-03 | Implement baseline: Match yesterday's observable benchmark daily, with contractual limits; also compare a fixed 10-bp band. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-05-REQ-04 | Fit/solve Impulse-control dynamic program with survival-calibrated borrower exits | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-05-REQ-05 | Evaluate incremental net fee dollars minus message labor and attrition loss | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-05-REQ-06 | Produce hold/reprice recommendation, approved band and counterfactual uncertainty | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-05-NFR-01 | No outbound fee message; policy must provide an auditable reason and retain borrower/owner rights as hard constraints. |
| QMG-20261116-05-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-05-AC-01 | GO if >=5% net revenue improvement with bootstrap lower bound >0 and balance loss <=2% in a pre-registered eligible cohort; no subgroup >5% deterioration. STOP if benefit relies on unobserved rejected requests or violates agreed repricing rights. |
| QMG-20261116-05-AC-02 | Set negotiation and exit costs to zero: the optimal inaction band should collapse under an otherwise frictionless model; rejected proposals must never become realized fees. |
| QMG-20261116-05-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Existing-loan fee changes, proposal/acknowledgment timestamps, rejected changes, borrower exits, balances, fee benchmarks and support-message labor. A contributed fee panel alone cannot identify retention elasticity. Clock: Review at 10:00 local market time with benchmark releases and acknowledgments available by 09:55. Use an effective fee only after both contractual acceptance and booking; no retroactive filled proposals. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Repricing is endogenous to scarcity and relationship quality. Off-policy evaluation cannot fix zero action overlap; randomized eligible shadow suggestions need business approval. Illustrative $400m existing balances; not a new trading strategy. Control concentration and fee elasticity; bps benefit must be net of exits, source revenue sharing and labor. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: Medium-high: measurable market-design frictions and interpretable control boundaries.
