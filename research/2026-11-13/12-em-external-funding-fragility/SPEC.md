# SPEC — EM External-Funding Fragility via Currency Mismatch and IIP
**ID:** QMG-20261113-12 · **Status:** Draft; human approval required · **Category:** B · Domestic & global markets · **Geography:** Brazil, Mexico, South Africa, Indonesia, India and selected EM sovereigns

## Problem and decision
A country can appear resilient on debt/GDP yet be fragile to dollar funding when external liabilities and liquid FX buffers have unfavorable maturity or currency composition.
**Decision supported:** Size EM FX downside budgets and sovereign duration exposures before external-funding shocks.

## H1 versus H0
**H1:** Release-vintage normalized foreign-currency credit-to-external-assets mismatch predicts EM stress windows beyond carry and spot volatility.
**H0:** A cost-inclusive Traditional sovereign credit rating tier, FX carry and three-month realized volatility. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
Fragility_c,t=(FX_credit_c,t - liquid_FX_assets_c,t)/GDP_c,t + λ*short_debt_service_c,t; optimize w for worst-case loss
```
c denotes country; all stocks denominated in comparable FX units; FX-credit and external-assets proxies can have incompatible reporting definitions requiring explicit normalization.
**Capacity and eligibility:** Use liquid EM FX forwards/ETFs only where available; include carry, forward points, market depth and capital controls.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
IMF IIP, BIS global liquidity quarterly FX credit, OECD macro where available, public reserve series and FX/sovereign returns. **Observation grain:** country × reporting quarter × first-public-availability time. **Decision horizon:** quarterly risk changes after actual statistical release; never refresh historic positions with today's revised values.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Size EM FX downside budgets and sovereign duration exposures before external-funding shocks. | Must |
| REQ-002 | Reproduce feasible benchmark: Traditional sovereign credit rating tier, FX carry and three-month realized volatility. | Must |
| REQ-003 | Implement candidate Point-in-time standardized funding mismatch factor with recession/regime interactions. only after benchmark | Must |
| REQ-004 | Report EM FX crash recall, max drawdown, FX-adjusted stress Brier, portfolio VaR breaches. and matched capacity/execution economics | Must |
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
USD $125k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$355k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 184%**. NOT forecast or historical measurement. Economic lever: hypothetical liquid $15m EM risk allocation where a small fraction of crash drawdown is avoided; no empirical hedge benefit.. Source availability: BIS GLI and IMF IIP published quarterly with varying country coverage and revisions.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Global liquidity metrics are quarterly; imputed weekly updates are model estimates, not observations.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if stress recall or drawdown control fails to beat carry-vol baseline in holdout crises.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
