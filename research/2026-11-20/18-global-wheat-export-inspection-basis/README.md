# Wheat Export Inspection Revisions to Global Basis and Calendar Spreads
**Project ID:** QMG-20261120-18 · **Category:** DOMESTIC & GLOBAL MARKETS · **Score:** 88/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
US, Black Sea and international wheat futures/physical flows. Weekly port inspection momentum and monthly USDA supply tables arrive at different times and may contain meaningful revisions.

**Decision:** Hedge wheat calendar spreads around official export inspection versus world balance-sheet information releases.

## Explicit falsifiable research question
Vintage-corrected inspection surprises anticipate regional wheat basis and nearby-deferred spread movements beyond seasonality and WASDE.

## Mathematical objective (research formulation, not calibrated)
```text
BasisChange_{r,t+h}=alpha+beta*(InspectionsPublished_t-ExpectedInspections_t)+gamma*Weather_t+epsilon
```
**Variables and hard constraints:** r region; expected inspections estimated using only pre-release history; h is post-release decision horizon with realistic market access.

## Data and timing
**Required:** USDA AMS export grain inspections dashboard, USDA wheat supply/price tables, official crop calendars, futures curves and export policy announcement records. **Observation grain:** weekly USDA inspection release × grain class × destination × exchange quote timestamp. **As-of rule:** USDA dashboard launched Oct 14 2026 and wheat tables updated Nov 12 2026; do not replace historic reports with latest annual revisions.

## Design options
- **Feasible baseline:** Monthly seasonal wheat spread regression using last known WASDE.
- **Candidate research method:** Mixed-frequency distributed-lag export surprise model.
- **Advanced counterfactual:** Structural Bayesian crop-flow network with regional stock constraints and censoring.
- **Metrics:** spread forecast delta, regional basis tracking, net slippage-adjusted hedge P&L, regime robustness.
- **Falsification / no-go:** No predictive improvement after weather, futures calendar effects and contemporaneous official release lags.
- **Primary leakage and identification risk:** Weekly inspections differ from actual export commitments; Black Sea supply and policy announcements may dominate..

## Economic and production screening
CME wheat futures tick, spread roll, physical basis accessibility and region transport costs.

**Difficulty:** High; **production feasibility:** Medium; **publication value:** Mixed-frequency official export releases and wheat basis transmission.
**24-month ROI sensitivity:** $175k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $100k / $265k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.6% / 89.3%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Unlike Australian water allocation/crop basis, uses multinational export timing, inspection vintages and wheat calendar spreads.
- **USDA grain export inspection dashboard announcement** (official dataset announcement, 2026-10-14): [official source](https://www.ams.usda.gov/content/usda-launches-export-grain-inspection-dashboard). Weekly inspection data, not necessarily contractual export sales.
- **USDA ERS wheat supply/demand/price data** (public dataset, updated 2026-11-12): [official source](https://ers.usda.gov/data-products/wheat-data). WASDE estimates and revised historical tables need real-time vintage archives.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
