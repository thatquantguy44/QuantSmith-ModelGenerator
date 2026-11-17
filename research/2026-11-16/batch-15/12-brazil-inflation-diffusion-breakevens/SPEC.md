# Specification — Brazil Inflation Diffusion versus Breakeven Carry

**QMG-20261116-12 · B — Domestic/global quant markets · research design, empirical state BLOCKED.**

## Decision and hypothesis

Choose a DV01-neutral nominal-versus-inflation-linked bond overlay using released inflation breadth and survey dispersion. Inflation-breadth revisions and Focus dispersion improve next-quarter breakeven return forecasts by at least 10% squared-error reduction versus carry plus headline surprise, and add 20 annualized net bps at fixed risk.

```text
y_t=R_linked,t:t+63-h_t*R_nominal,t:t+63-index_carry_t; y_t=alpha+beta*diffusion_t+gamma*dispersion_t+delta*carry_t+epsilon; DV01_linked-h_t*DV01_nominal=0, |gross_DV01|<=K
```

R are local-currency total returns; h matches nominal to real-bond DV01 with residual inflation sensitivity reported; diffusion share of component price increases known at release; dispersion survey disagreement; index_carry mechanically known accrued indexation; K risk budget. USD investor FX exposure is hedged and charged separately.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-12-REQ-01 | Ingest inflation release x survey public version x matched bond pair | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-12-REQ-02 | Build released inflation diffusion, survey dispersion and known indexation carry | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-12-REQ-03 | Implement baseline: Carry/roll plus headline inflation surprise using a fixed ridge regression and identical risk budget. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-12-REQ-04 | Fit/solve Sparse distributed-lag regression with local-projection diagnostics | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-12-REQ-05 | Evaluate 63-session DV01-neutral excess breakeven return net of mechanical carry | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-12-REQ-06 | Produce breakeven forecast, DV01 hedge and market-access gate | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-12-NFR-01 | Unresolved official IPCA component source, tax convention or vintage timestamp blocks any empirical claim; all returns retain BRL and hedged-USD views. |
| QMG-20261116-12-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-12-AC-01 | GO if >=10% forecast MSE improvement and >=20 net annualized bps at unchanged risk with >=40 nonoverlapping quarterly outcomes; STOP if official component vintage or executable curve history cannot be established. |
| QMG-20261116-12-AC-02 | Set nominal and linked yields to parallel shifts with no inflation shock: residual P&L must reflect declared duration mismatch, not be mislabeled inflation alpha. |
| QMG-20261116-12-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

BCB public inflation/Focus releases, component-level official IPCA data to be resolved before implementation, dated expectations distributions, bond cash flows/indexation conventions, executable nominal and real curves and BRL hedge quotes. Clock: Trade no earlier than next Sao Paulo session after verified inflation and survey publication, with one-hour processing lag. Survey collection dates are never treated as public timestamps. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Overlapping quarterly labels create false sample size; inflation indexation/tax rules and market-access costs can erase apparent returns. No current Brazilian tax recommendation is assumed. Illustrative $40m duration-matched overlay; constrain pair DV01 and <=1% of observed issue turnover. Local liquidity, BRL hedging, indexation and applicable taxes must be priced before investment use. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: High if public component vintages can be assembled; tests information diffusion separately from mechanical indexation.
