# Public BDC Portfolio Fair-Value Markdown Lead Indicator
**Project ID:** QMG-20261120-17 · **Category:** DOMESTIC & GLOBAL MARKETS · **Score:** 89/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
US public BDC equities, leveraged loans and credit sentiment. Quarterly fair values of less-liquid loans are not continuous market prices; comparability and valuation lag impair credit monitoring.

**Decision:** Prioritize due diligence or credit hedges where public business development company holdings imply delayed loan fair-value marks.

## Explicit falsifiable research question
Public issuer-level BDC portfolio mark dispersion identifies future credit event/downgrade risk after controlling for BDC leverage and macro credit spread.

## Mathematical objective (research formulation, not calibrated)
```text
RiskScore_{loan,t}=f(PriceToCost_{t},NonAccrual_{t},Sector_{t},FundLag_{t})
```
**Variables and hard constraints:** PriceToCost is reported fair value over cost, nonaccrual flags only as filed, FundLag is filing delay; target is future externally validated credit deterioration.

## Data and timing
**Required:** Original SEC BDC 10-Q/10-K investment schedules and mark values, sector classification, publicly known credit outcomes and licensed leveraged-loan pricing. **Observation grain:** BDC filing × portfolio company/sector × disclosure timestamp. **As-of rule:** Use filed investment schedules only after filing acceptance; amendments/revised portfolio marks cannot enter historical quarters.

## Design options
- **Feasible baseline:** BDC aggregate NAV discount and published nonaccrual percentage.
- **Candidate research method:** Issuer-level mark-hazard panel with censored holdings and missing-not-at-random controls.
- **Advanced counterfactual:** Hierarchical Bayesian marked-to-market credit migration model with portfolio network dependence.
- **Metrics:** future credit-event AUC/PR, mark-calibration error, NAV stress accuracy, opportunity capacity.
- **Falsification / no-go:** No improvement over current NAV discount/nonaccrual baseline in later quarters or effects only known after financial reports.
- **Primary leakage and identification risk:** BDC portfolio company identities, valuation methods and distressed sales are not uniformly disclosed; matching bias..

## Economic and production screening
BDC equity market depth, credit hedging basis, optional loan trading access and stale valuation discounts.

**Difficulty:** High; **production feasibility:** Medium; **publication value:** Private-credit valuation smoothing and public disclosure information lag.
**24-month ROI sensitivity:** $190k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $115k / $275k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -29.4% / 68.9%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Distinct from CMBS maturity/refinance hazard and TRACE ETF NAV stress: tests *BDC marked private loan holdings*.
- **SEC EDGAR API documentation** (public data API, updated 2025-04-08): [official source](https://www.sec.gov/search-filings/edgar-application-programming-interfaces). Companyfacts is not a complete source of issuer/customer segmentation or historical index membership.
- **SEC developer resources and disclosure revisions** (public filings methodology, checked 2026-11-20): [official source](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data). Public filings can be corrected; store original accepted filing before any update.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
