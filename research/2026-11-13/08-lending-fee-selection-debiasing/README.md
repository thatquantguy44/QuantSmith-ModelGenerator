# Securities-Lending Fee Observability & Selection-Bias Corrector
**A · Securities finance** · **Priority 88/100** · **Difficulty Medium-high** · **Feasibility: Medium-high** · **Publication interest 5/5 (conceptual, not a paper).**

## Why this exists
Published securities-loan fee samples cover executed and contributed loans unevenly; rare specials and failed locates can be missing non-randomly.

**Market / geography:** US/global securities lending benchmarks. **Asset classes:** stock-loan fee surfaces and market-data science.

## Falsifiable hypothesis and investment/operational decision
Explicit observability weighting and partial identification shrink apparent fee benchmark error versus sample-weighted means on contributor holdouts.

**Decision:** Publish uncertainty-aware fee benchmarks and abstain from quote-setting when selected sample coverage is inadequate..

## Research model
```text
mu_hat = Σ_i w_i*y_i/Σ_i w_i; w_i=1/P(observed_i|X_i); report sensitivity to unidentified selection
```
y_i is observed fee; X_i observable security/liquidity/context; propensity weights are estimated from an externally validated sample frame.

## Data and decision clock
Contributed executed fee samples; public security volume/short-interest proxies; locate response metadata; source coverage and revisions. **Observation grain:** security × lending day × vendor/contributor population. **Decision horizon:** benchmark at next published cutoff; never use end-of-day contributions before receipt.

## Baseline versus candidate
- **Baseline:** Daily equally weighted or outstanding-value-weighted observed market fees.
- **Proposed model:** Doubly robust weighting with overlap and selection-sensitivity intervals.
- **Advanced option:** Bayesian selection model with unverifiable missing-not-at-random stress bounds.
- **Primary metrics:** cross-contributor benchmark error, interval coverage, abstention, quote drift, market breadth coverage.
- **Falsification:** Reject if cross-contributor MAE reduction <10% or intervals under-cover known withheld contributions.
- **Primary economic or methodological caveat:** Missing-not-at-random selection cannot be identified from executed loans alone; confidence intervals can be falsely narrow.

## 24-month ROI sensitivity (unverified assumptions only)
USD $120k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $45k–$230k over 24 months. Net ROI = (gross benefit − cost)/cost = **-62% to 92%**. NOT forecast or historical measurement. Economic lever: scenario: avoid mispriced lending quotes on a small subset of specials; savings not inferable from the public sources alone.

## Execution, capacity and feasibility
Primarily an internal benchmark/data product; no automatic quoting when source coverage or liquidity is inadequate.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
