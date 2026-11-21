# Japan FX Intervention Impact and Option-Skew Persistence
**Project ID:** QMG-20261120-11 · **Category:** DOMESTIC & GLOBAL MARKETS · **Score:** 97/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
Japan USD/JPY, yen crosses and FX options. Official intervention disclosures arrive after execution; a hindsight backtest can misrepresent a trader's knowledge of actual intervention days.

**Decision:** Determine when to reduce/hedge yen exposure following **publicly observed** intervention or subsequent official disclosure.

## Explicit falsifiable research question
A release-time-corrected intervention-event measure predicts conditional 1–20-day FX variance/skew adjustment beyond macro announcements and momentum.

## Mathematical objective (research formulation, not calibrated)
```text
DeltaSkew_{t,h}=beta*InterventionKnownAt_t+gamma*MacroControls_t+epsilon_{t,h}
```
**Variables and hard constraints:** InterventionKnownAt_t is zero until event is publicly known or release issued; h is forward horizon, and skew is an executable options quote measure.

## Data and timing
**Required:** MOF monthly/quarterly intervention releases and dates, spot FX, short-term rate differential, timestamped USDJPY options/forward data. **Observation grain:** intervention disclosure event × FX option tenor × quote timestamp. **As-of rule:** MOF 2026 Q3 intervention details published Nov 9, 2026; never use ex-post intervention date labels in same-day live-time signals.

## Design options
- **Feasible baseline:** Standard spot momentum and monetary-policy announcement dummy.
- **Candidate research method:** Disclosure-timestamp event study with matched controls and local projections.
- **Advanced counterfactual:** Partial-identification causal synthetic control separating information, execution and portfolio-flow channels.
- **Metrics:** incremental forward skew/vol forecast skill, delta-hedged net P&L, placebo events, risk-adjusted drawdown.
- **Falsification / no-go:** No differential response versus rate/central-bank news controls on withheld intervention disclosures or net-option-cost results.
- **Primary leakage and identification risk:** Actual intervention execution is not transparently known in real time; small event count undermines causal certainty..

## Economic and production screening
Executable FX spot/options spreads, liquidity, event jump exposure, market access and derivatives capital.

**Difficulty:** High; **production feasibility:** High for event research; trade evidence conditional; **publication value:** Identification of FX intervention signaling under delayed official disclosure.
**24-month ROI sensitivity:** $180k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 8 months; annual gross benefit scenarios $0k / $95k / $240k (downside/base/upside) for the remaining 1.3333333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -29.6% / 77.8%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Distinct from multilingual monetary policy semantic shocks; targets executed FX operations and retrospective labeling bias.
- **Japan Ministry of Finance — 2026 Q3 intervention breakdown** (official data, 2026-11-09): [official source](https://www.mof.go.jp/english/policy/international_policy/reference/feio/quarter/2026_3Qe.html). July 30–Aug 3 2026 operations disclosed in later quarterly release; cannot use details before release.
- **Japan Ministry of Finance — FX intervention monthly release index** (official data, latest index checked 2026-11-20): [official source](https://www.mof.go.jp/english/policy/international_policy/reference/feio/monthly/index.html). Public monthly aggregate reports lag intervention days; do not make same-day predictions with ex-post labels.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
