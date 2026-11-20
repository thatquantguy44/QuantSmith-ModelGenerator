# Evergreen Repo Early-Termination Optionality Risk Budget
**Project ID:** QMG-20261120-09 · **Category:** SECURITIES FINANCE · **Score:** 87/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
Open and evergreen secured funding agreements. Contractual call/notice periods create embedded funding options not captured by standard fixed-maturity repo carry.

**Decision:** Set rate/tenor risk charges for unilateral termination and extension rights in open repo or evergreen funding.

## Explicit falsifiable research question
Notice-option-adjusted funding pricing reduces out-of-sample replacement-cost surprises versus duration-only term curve cost.

## Mathematical objective (research formulation, not calibrated)
```text
V_t=max(ExerciseValue_t, Carry_t+discount*E_t[V_{t+1}]) subject to NoticeDays,Eligibility
```
**Variables and hard constraints:** exercise and continuation are contract-party-specific; funder and borrower exercise incentives must be separately simulated.

## Data and timing
**Required:** Synthetic open-repo terms, public SOFR and OFR repo curve history, legally enforceable reset/termination terms and funding costs. **Observation grain:** contract × notice period × funding day × interest-rate state. **As-of rule:** Public repo rates have release lags; exact contract termination rights must be known at contract initiation, not retrofitted.

## Design options
- **Feasible baseline:** Static repo spread plus deterministic notice-day funding reserve.
- **Candidate research method:** Least-squares Monte Carlo for bilateral asymmetric stop decisions.
- **Advanced counterfactual:** Nonzero-sum stochastic game with liquidity-dependent termination intensities.
- **Metrics:** replacement funding loss, option premium calibration, cash-flow stress, tail liquidity gap.
- **Falsification / no-go:** Option charge unstable or no improvement over conservative notice reserve in stress holdouts.
- **Primary leakage and identification risk:** Non-observed counterparty exercise behavior; public term repo alone does not identify proprietary notice clauses..

## Economic and production screening
Bilateral notice terms, term borrowing capacity, haircuts and closeout spreads constrain exercise decisions.

**Difficulty:** High; **production feasibility:** Medium; **publication value:** Bilateral termination-option pricing in secured funding.
**24-month ROI sensitivity:** $180k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $105k / $270k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -31.9% / 75.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Prior repo term-structure forecasting models *fixed-tenor spreads*; this values unilateral open-term exercise mechanics.
- **OFR U.S. Repo Markets Data Release** (public data, current methodology page; checked 2026-11-20): [official source](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/). Cleared rates typically T+1; tri-party T+2; participant-level graph not public.
- **SEC Treasury Clearing Implementation** (regulatory source, checked 2026-11-20): [official source](https://www.sec.gov/featured-topics/treasury-clearing-implementation). Shows Dec 31 2026 eligible cash and June 30 2027 eligible repo dates; check exemptions.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
