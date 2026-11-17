# Specification — US CMBS Refinance Hazard from Public Disclosures

**QMG-20261116-19 · B — Domestic/global quant markets · research design, empirical state BLOCKED.**

## Decision and hypothesis

Limit public CMBS/REIT credit exposure according to released refinance cash-flow gaps and competing maturity outcomes. A vintage-safe competing-risk model improves 12-month refinancing-distress Brier score by at least 10% versus maturity wall plus current DSCR and lowers stress portfolio loss by 5% at equal spread carry.

```text
h_k(t|X)=P(event_k at t|survival_t,X_available); gap=max(balance-LTV_max*NOI/cap_rate,0); min_w CVaR_95(loss(w,h))+lambda*turnover, spread_carry>=C, issuer_weight<=0.05
```

k is refinance, extension, modification or distress; NOI net operating income as publicly reported; cap_rate scenario valuation yield; LTV_max declared refinance limit; w bond/issuer exposures; C baseline spread-carry floor. Scenario cap rates are assumptions, not current appraisals.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-19-REQ-01 | Ingest loan x public reporting vintage x maturity/outcome event | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-19-REQ-02 | Build public refinance cash gap, maturity hazard and amendment lineage | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-19-REQ-03 | Implement baseline: Logistic distress model using months-to-maturity and last publicly available DSCR with fixed rate-shock scenarios. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-19-REQ-04 | Fit/solve Competing-risk survival model with refinance cash-gap covariates | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-19-REQ-05 | Evaluate 12-month competing refinance outcomes and portfolio loss at fixed spread carry | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-19-REQ-06 | Produce competing-outcome probabilities, missing-field coverage and tranche mapping limits | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-19-NFR-01 | Require filing accession and field-level source path; unparsed or contradictory outcome definitions fail closed for that loan. |
| QMG-20261116-19-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-19-AC-01 | GO if Brier improves >=10% and stress loss falls >=5% at same carry over a held-out issuance vintage; STOP if modification histories, exited loans or outcome timing are missing for >10% of sample. |
| QMG-20261116-19-AC-02 | Replace an original loan maturity with a later extension and verify earlier features remain unchanged; include liquidated loans and enforce waterfall conservation under default scenarios. |
| QMG-20261116-19-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Public ABS-EE/10-D/10-K filings, accepted timestamps, loan maturity/amendment histories, NOI/DSCR field definitions, property type, rate terms and outcome reports; licensed bond/REIT pricing and servicing histories as needed. An example filing does not establish complete coverage. Clock: Update risk after SEC acceptance plus one business day parsing/review; a prior reporting month's NOI remains unavailable until filing. Amendments are appended and never rewrite earlier risk snapshots. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Surviving securitizations and amended files omit failed/removed loans; appraisals lag. Tranche waterfalls and selection into public deals prevent loan-level risk from mapping directly to bond P&L. Illustrative $50m credit exposure; position limits depend on tranche liquidity and loss subordination. No assumption that a loan risk score is directly tradable or every CMBS has a liquid hedge. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: High: public disclosure vintages and competing refinancing paths; publication depends on reliable field extraction and sample representativeness.
