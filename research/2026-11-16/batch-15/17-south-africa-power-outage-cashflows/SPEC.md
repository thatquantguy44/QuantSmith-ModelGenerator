# Specification — South African Power Reliability Equity Exposure

**QMG-20261116-17 · B — Domestic/global quant markets · research design, empirical state BLOCKED.**

## Decision and hypothesis

Build a sector/beta-neutral equity hedge against power-supply deterioration using pre-disclosed operational exposure. Exposure-weighted unplanned generation losses explain cash-flow/return sensitivity beyond national load-shedding stage, improving an outage hedge's downside loss by at least 10%.

```text
R_it=alpha_i+date_t+beta*(exposure_i,pre*outage_t)+Gamma*controls_it+epsilon_it; min_w Var(R_portfolio-w'R_hedge)+k*turnover; beta_market'w=0, sector'w=0, |w_i|<=0.03
```

exposure_pre is firm energy intensity and backup dependence measured from disclosures before the study window; outage released unplanned unavailable capacity; R returns; controls include lagged commodity and FX factors; w hedge weights. beta is associational unless an independently defensible exogeneity design survives.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-17-REQ-01 | Ingest firm x day and dated generation/outage release | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-17-REQ-02 | Build pre-disclosed energy intensity, backup coverage and released outage innovation | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-17-REQ-03 | Implement baseline: National load-shedding stage interacted with fixed sector averages and a market/FX hedge. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-17-REQ-04 | Fit/solve Panel fixed effects with pre-period exposure interactions and event-placebo tests | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-17-REQ-05 | Evaluate power-shock residual equity sensitivity and hedge downside error | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-17-REQ-06 | Produce firm sensitivity bounds and neutral power-risk hedge research basket | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-17-NFR-01 | Any exposure inferred from a later filing is unavailable for earlier dates; preserve source language and disclosure spans. |
| QMG-20261116-17-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-17-AC-01 | GO if downside hedge error improves >=10%, coefficient sign is stable in held-out periods and net benefit survives doubled spreads; STOP causal interpretation if pretrends or commodity/FX confounds remain. |
| QMG-20261116-17-AC-02 | Use a future outage series as a placebo and randomize exposure labels within sectors; the real-time pipeline must reject future features and significance should vanish under label randomization. |
| QMG-20261116-17-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Eskom public system/outage releases, exact publication versions, issuer public energy/backup disclosures, geography, sector, JSE returns including delistings, ZAR and commodity controls. Historical spatial outage maps are an unresolved source gate. Clock: Update after verified Eskom publication; act next JSE session with prior-disclosed firm exposures. Never label realized electricity usage as known before earnings disclosure. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Power failures can reflect economic demand and maintenance choices; common national shocks do not supply clean quasi-random variation. Firms adopting solar are selected, and disclosure histories are incomplete. Illustrative $20m hedge sleeve capped at 1% ADV with local spreads, market access and ZAR hedge costs; concentrated names can exhaust capacity rapidly. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: High if exposure and timing can be made public and causal limits are respected; a careful negative result is valuable.
