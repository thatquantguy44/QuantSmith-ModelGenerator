# Specification — US–Europe Corridor Variance and Jump-Risk Budget

**QMG-20261116-16 · B — Domestic/global quant markets · research design, empirical state BLOCKED.**

## Decision and hypothesis

Allocate a limited short-corridor-variance risk budget across US and European indices while purchasing a defined tail hedge. A corridor/jump-aware allocation reduces 99% tail loss by at least 15% at equal net carry versus equal-vega short-variance with the same tail-hedge budget.

```text
max_w E[carry(w)]-lambda*CVaR_99(PnL_loss(w)); corridor_RV=sum_k r_k^2*1{L<S_(k-1)<U}; jump_proxy=RV-bipower; |vega_j|<=V_j, stress_loss<=K, hedge_cost<=H
```

r high-frequency log return; L,U predetermined corridor levels; bipower is a training-fixed continuous-variation estimator; j market; w executable option-strip weights; V vega caps; K stress loss limit; H tail premium budget. Corridor payoff convention must match available instruments; VIX itself is not the trade.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-16-REQ-01 | Ingest market x option expiry/strike x quote instant plus intraday underlying bars | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-16-REQ-02 | Build corridor variance, overnight jump proxies, executable strip costs and tail hedge Greeks | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-16-REQ-03 | Implement baseline: Equal-vega option-strip variance exposure by market with a fixed put-spread tail hedge and identical costs. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-16-REQ-04 | Fit/solve Semiparametric continuous/jump decomposition and constrained risk-budget allocation | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-16-REQ-05 | Evaluate net option-strip carry and stress/tail loss at fixed hedge premium | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-16-REQ-06 | Produce vega allocation, explicit option-strip positions and stress funding requirements | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-16-NFR-01 | Reject crossed/stale quotes and impossible option monotonicity; no interpolation may create executable liquidity that was not quoted. |
| QMG-20261116-16-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-16-AC-01 | GO if >=15% ES reduction with mean net carry within 5% of baseline across >=8 years including held-out stress; STOP if benefit fails under doubled option spreads or cannot be implemented by listed strips. |
| QMG-20261116-16-AC-02 | Insert a large overnight gap with no intraday prints: loss and jump exposure must remain visible; an apparent free option caused by zero/stale bid must be rejected. |
| QMG-20261116-16-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Public index methodology for background, synchronized bid/ask option chains, index/futures returns, expiries, dividends, rates and settlement rules. Intraday sampling and overnight jump handling are fixed before testing. Clock: Allocate at a common UTC snapshot when both markets have liquid executable quotes; use prior completed return bars only. Do not pair a European close with later US data as contemporaneous. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Sparse extreme events, stale deep-OTM quotes, mid-price replication and model-selected sampling can manufacture carry. Margin calls and holiday mismatches can dominate option premium. Illustrative $20m capital budget with explicit vega/margin limits, <=1% option-strike volume/open-interest bounds and no unlimited tail-risk assumption. Capacity likely concentrated in a few liquid expiries. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: High methodological potential; a crowded literature means exact corridor and jump novelty needs further review.
