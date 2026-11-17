# Specification — Owner Co-Withdrawal Limits for Lendable Inventory

**QMG-20261116-07 · A — Securities finance · research design, empirical state BLOCKED.**

## Decision and hypothesis

Cap loans supported by correlated sources and keep replacement options against simultaneous owner withdrawals. Tail co-withdrawal limits reduce 99th-percentile replacement cost by at least 15% versus owner-notional caps without sacrificing more than 2% normal lending revenue.

```text
max_x sum_o mu_o*x_o - lambda*CVaR_99(sum_o (x_o-S_o)^+*c_o); sum_o x_o<=D, 0<=x_o<=I_o, x_o<=k_o*I_total
```

o owner; x committed loan support; I available inventory; S scenario remaining supply; c replacement spread-cost converted to dollars; D demand; mu net expected fee per quantity; k owner concentration cap; lambda tail-cost aversion.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-07-REQ-01 | Ingest owner x security x dated available-inventory snapshot | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-07-REQ-02 | Build common withdrawal factor, owner lineage groups and replacement tail scenarios | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-07-REQ-03 | Implement baseline: Static 10% owner concentration cap with independent withdrawal probabilities. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-07-REQ-04 | Fit/solve Hierarchical common-factor withdrawal model and CVaR allocation | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-07-REQ-05 | Evaluate joint inventory-shortfall distribution and net cost of an allocation limit | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-07-REQ-06 | Produce source concentration limits and joint-withdrawal stress certificate | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-07-NFR-01 | No raw owner identity or positions in public artifacts; a private run must use pseudonymous IDs and lineage access controls. |
| QMG-20261116-07-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-07-AC-01 | GO if 99th-percentile cost improves >=15%, normal net revenue loss <=2%, and at least 3 distinct withdrawal episodes are held out; STOP if dependence is unidentified or fewer than 24 months of owner histories exist. |
| QMG-20261116-07-AC-02 | Duplicate an owner under two IDs: effective diversification must not improve; simulate perfect co-withdrawal and verify the model does not report independent-source protection. |
| QMG-20261116-07-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Permissioned daily available/withdrawn quantities by owner and security, mandate inception/termination, owner-group lineage, public N-PORT filings and known rebalance calendars. Public monthly/quarterly holdings are lagged aggregate context only. Clock: Set next-day inventory limits after local close using confirmed availability received by cutoff; public fund holdings enter at filing acceptance, not portfolio as-of date. Never condition on the owner's future sale or recall notice. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Mandate closure is not an iid recall; inactive and terminated owners must remain in the sample. Co-movement can be driven by security demand rather than shared owner behavior. Illustrative $500m supported inventory; direct benefits limited to replacement-cost savings and retained fee revenue. Extreme withdrawals may have no feasible replacement regardless of model. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: High if dependence is identifiable; otherwise honest bounds on inventory diversification are useful internal research.
