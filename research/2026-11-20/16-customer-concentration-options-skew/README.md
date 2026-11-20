# Issuer Customer-Concentration Disclosure to Earnings Options Skew
**Project ID:** QMG-20261120-16 · **Category:** DOMESTIC & GLOBAL MARKETS · **Score:** 90/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
US listed single-name equity options and SEC 10-K/10-Q issuers. A large customer share can create correlated revenue jump exposure not captured by standard sector-level realized volatility.

**Decision:** Hedge customer-loss jump risk in companies with concentrated customers using explicitly costed options structures.

## Explicit falsifiable research question
Point-in-time EDGAR customer concentration disclosures explain forward options downside skew changes beyond leverage, size and event vol.

## Mathematical objective (research formulation, not calibrated)
```text
DownsideSkew_{i,t}=a+beta*CustomerHHI_{i,t-known}+gamma*EventControls_{i,t}+epsilon
```
**Variables and hard constraints:** HHI is sum of squared disclosed customer revenue shares (bounded/partially observed); t-known is filing dissemination time, not fiscal year end.

## Data and timing
**Required:** SEC EDGAR original issuer filings, customer concentration disclosures, single-stock option surface, earnings calendar, liquidity and corporate actions. **Observation grain:** issuer accepted filing × reported customer share × options quote timestamp. **As-of rule:** Use SEC acceptance timestamps and first published disclosure, not retroactive tagged XBRL after amended filings.

## Design options
- **Feasible baseline:** Size/leverage/industry/earnings event-only option skew estimator.
- **Candidate research method:** Censored-disclosure panel with inverse observation probability adjustment.
- **Advanced counterfactual:** Jump-diffusion structural model of concentrated-customer exit hazard.
- **Metrics:** post-filing skew residual, risk hedge efficiency, delta-neutral net performance and disclosure coverage.
- **Falsification / no-go:** No post-filing incremental skew or hedge gain beyond conventional earnings-related jump risk.
- **Primary leakage and identification risk:** Customer concentrations may be anonymized and nonrandomly omitted; options trade data can be illiquid..

## Economic and production screening
Option open interest, bid/ask, assignment/maturity mechanics and volatile event hedging friction.

**Difficulty:** Medium-high; **production feasibility:** High for disclosure research, trading conditional; **publication value:** Disclosure censoring and implied tail-risk segmentation.
**24-month ROI sensitivity:** $160k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $85k / $260k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -33.6% / 103.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Prior Japan buyback execution, AI capex and global factors differ from customer-dependent equity jump risk around original filings.
- **SEC EDGAR API documentation** (public data API, updated 2025-04-08): [official source](https://www.sec.gov/search-filings/edgar-application-programming-interfaces). Companyfacts is not a complete source of issuer/customer segmentation or historical index membership.
- **SEC developer resources and disclosure revisions** (public filings methodology, checked 2026-11-20): [official source](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data). Public filings can be corrected; store original accepted filing before any update.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
