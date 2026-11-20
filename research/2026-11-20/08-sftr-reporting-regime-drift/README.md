# SFTR Reporting Regime Drift and Public-Private Divergence Detector
**Project ID:** QMG-20261120-08 · **Category:** SECURITIES FINANCE · **Score:** 88/100 (editorial) · **State:** proposal, no code/tests/empirical results.

## Market and decision
European securities financing transaction repositories. Registry revisions and reporting practice changes can masquerade as repo/securities-lending market shifts.

**Decision:** Detect structural reporting-quality breaks before using reported SFTR aggregates as market exposure signals.

## Explicit falsifiable research question
Joint change-point tests on volumes, missingness and reported collateral taxonomy identify synthetic or historical reporting breaks more reliably than absolute-value outlier rules.

## Mathematical objective (research formulation, not calibrated)
```text
Alarm_t=1{PosteriorP(change|feature_history)>q}; minimize detection_delay+lambda*false_alarms
```
**Variables and hard constraints:** q is alarm threshold chosen before holdout; changes attributed to reporting are hypotheses until repository audit.

## Data and timing
**Required:** ESMA reporting rules and publications, public aggregate exposures where available, historical methodology changes, synthetic backdated schema versions. **Observation grain:** SFTR public aggregate series × jurisdiction × report vintage. **As-of rule:** Use publication timestamps and repository versions, not reporting reference dates; detailed transaction data are supervisor-restricted.

## Design options
- **Feasible baseline:** Fixed ±3-sigma z-score alert on each series.
- **Candidate research method:** Robust multivariate Bayesian online change-point detection.
- **Advanced counterfactual:** Hierarchical regime/missingness change-point models with document version embeddings as covariates.
- **Metrics:** break detection delay, false alarms, post-correction economic interpretation stability.
- **Falsification / no-go:** Synthetic change fixtures not detected within agreed delay or false alerts exceed preregistered burden.
- **Primary leakage and identification risk:** Only public aggregate data may be available, making root-cause verification incomplete..

## Economic and production screening
Low runtime; review cost per alert and regulator/source availability dominate feasibility.

**Difficulty:** Medium; **production feasibility:** High for aggregate checks; **publication value:** Public regulatory-data integrity and market microstructure inference.
**24-month ROI sensitivity:** $135k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $90k / $190k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 0.0% / 111.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.

## Evidence and novelty
Prior identity reconciliation matches transactions across books; this detects public reporting *regime and taxonomy changes*.
- **ESMA Securities Financing Transactions Reporting** (regulatory source, current reporting framework checked 2026-11-20): [official source](https://www.esma.europa.eu/data-reporting/sftr-reporting). Public reports are aggregates; transaction-level SFTR is permissioned.
- **ESMA trade-repository SFTR enforcement release** (regulatory enforcement, 2026-02-19): [official source](https://www.esma.europa.eu/press-news/esma-news/esma-sanctions-regis-tr-serious-breaches-organisational-obligations). Shows the economic importance of SFTR data quality; not specific model performance evidence.

## Navigation
[Spec](SPEC.md) · [Plan](PLAN.md) · [Tasks](TASKS.md) · [Roadmap](ROADMAP.md) · [Handoff](HANDOFF.md) · [Sources](SOURCES.md) · [Agent](AGENT.md) · [Skill](SKILL.md) · [Prompt](PROMPT.md) · [Tooling](TOOLING.md) · [Workflow](WORKFLOW.md) · [Runtime](RUNTIME.md) · [Evals](EVALS.md)

**Research design only.** Market data, human approval, trading capabilities and deployable software do not yet exist in this folder.
