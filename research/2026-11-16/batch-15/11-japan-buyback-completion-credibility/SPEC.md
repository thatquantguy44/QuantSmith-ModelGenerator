# Specification — Japan Buyback Completion Credibility

**QMG-20261116-11 · B — Domestic/global quant markets · research design, empirical state BLOCKED.**

## Decision and hypothesis

Weight an announcement-event equity sleeve by ex-ante completion probability rather than headline authorized buyback size. Completion-weighted signals improve 60-trading-day sector/beta-neutral net returns by at least 50 bps per annum versus authorization-size signals, after 30 bps round-trip costs.

```text
p_i=P(completion_i>=0.8*authorization_i by expiry|X_at_announcement); s_i=p_i*authorized_value_i/float_cap_i; max_w s'w-lambda*w'Sigma*w-k*||w-w_prev||_1; sum w=0, beta'w=0, |w_i|<=0.02
```

i announced program; X includes previously filed completion history, cash constraints and program terms; p calibrated probability; s expected completion intensity; w portfolio weights; Sigma lag-only covariance; k transaction charge. Announced future execution never enters X.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-11-REQ-01 | Ingest issuer x announced buyback program x filing acceptance event | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-11-REQ-02 | Build prior completion rate, cash-funded capacity, expiry horizon and free-float-normalized authorization | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-11-REQ-03 | Implement baseline: Authorization divided by contemporaneously known float market cap, with the same neutral portfolio and execution rules. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-11-REQ-04 | Fit/solve Calibrated discrete-time completion hazard with constrained event portfolio | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-11-REQ-05 | Evaluate program completion probability and 60-day residual equity return | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-11-REQ-06 | Produce completion probabilities and neutral event-sleeve research orders | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-11-NFR-01 | Retain Japanese original text, accession ID and extraction span; any translation/model extraction without supporting span is excluded. |
| QMG-20261116-11-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-11-AC-01 | GO if completion Brier improves >=10% and net return uplift >=50 annualized bps with block-bootstrap lower bound >0 over >=200 programs and a held-out year; STOP on missing delistings or gains concentrated in inaccessible prints. |
| QMG-20261116-11-AC-02 | Shift completion filings to their reporting-period end: leakage checker must reject the join; include terminated programs and delisted issuers with zero future authorization assumed. |
| QMG-20261116-11-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Public issuer/EDINET buyback announcements and monthly completion filings, JPX procedures, cancellation/reissue terms, sector/free-float history, delisted returns and licensed executable prices. J-Quants Pro is a licensed convenience, not assumed free bulk access. Clock: Enter at next Tokyo session VWAP after a public announcement plus 30 minutes processing; filings arriving after the next-open cutoff shift another session. Completion reports update only when publicly filed. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Completion is endogenous to stock prices, governance changes and earnings; predictive results do not establish buyback causation. Current issuer lists produce survivorship bias. Illustrative $25m beta-neutral sleeve; cap each trade at 1% of lagged ADV, use local spreads, impact and shorting costs. Thin small-cap programs may have little scalable edge. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: High: completion credibility and execution mechanism heterogeneity; causal claims require stronger identification than prediction.
