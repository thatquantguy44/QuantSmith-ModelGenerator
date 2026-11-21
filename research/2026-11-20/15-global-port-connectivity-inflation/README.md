# Global Shipping Connectivity Re-Routing to Inflation and Equity Margins
**Project ID:** QMG-20261120-15 · **Category:** DOMESTIC & GLOBAL MARKETS · **Score:** 91/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
East Asia–Europe–US maritime routes, transport/industrial equity sectors. Freight disruption signals are often conflated with trade quantities, while shipping network redundancy alters price transmission under port outages.

**Decision:** Size logistics/inflation hedges when public route connectivity and port-service centrality shift.

## Explicit falsifiable research question
Route-centrality-adjusted connectivity changes improve delayed goods-inflation and shipper-margin forecasts over raw container volume.

## Mathematical objective (research formulation, not calibrated)
```text
DeltaP_{r,t+h}=sum_p Exposure_{r,p}*Shock_{p,t}/(1+AlternateRoutes_{p,t})+epsilon
```
**Variables and hard constraints:** r is importer region, p port corridor; shocks and alternate route count must use actually published index vintage.

## Data and timing
**Required:** UNCTAD monthly/quarterly liner connectivity, MARAD freight/port dashboards, shipping rate indexes where licensed, CPI/PPI and issuer logistics costs. **Observation grain:** country/port route × monthly index release × subsequent inflation/earnings outcome. **As-of rule:** UNCTAD latest confirmed index data update Sep 28 2026; a 2026-11-20 decision cannot use December data.

## Design options
- **Feasible baseline:** Aggregate global shipping index versus region CPI with fixed lag.
- **Candidate research method:** Supply-route network exposure local projections.
- **Advanced counterfactual:** Causal graph shock transmission with endogenous alternative route capacity and measurement error.
- **Metrics:** inflation nowcast gain, equity margin dispersion, attribution stability and hedged net P&L.
- **Falsification / no-go:** No incremental signal after global industrial production, oil and published trade volume controls.
- **Primary leakage and identification risk:** Connectivity is not real-time port congestion and quarterly updates can obscure freight cycle timing..

## Economic and production screening
Sector ETF/futures depth, global market close mismatch, FX hedge and rebalance slippage.

**Difficulty:** High; **production feasibility:** Medium; **publication value:** Shipping network redundancy and inflation pass-through identification.
**24-month ROI sensitivity:** $220k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $135k / $300k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.4% / 59.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Batch-14 trade-network export shock model uses reported trade value; this studies route topology and alternate maritime connectivity.
- **UNCTAD — Liner shipping connectivity and updates** (public dataset, monthly index updated 2026-09-28): [official source](https://unctadstat.unctad.org/insights/theme/111). Monthly network connectivity index not high-frequency port congestion; check methodology revisions.
- **U.S. MARAD port data and statistics** (public datasets portal, checked 2026-11-20): [official source](https://www.maritime.dot.gov/data-reports/ports). Some datasets/proprietary vessel calls are not publicly redistributable.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
