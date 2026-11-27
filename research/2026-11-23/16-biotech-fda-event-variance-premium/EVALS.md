# EVALS — Biotech FDA Catalyst Probability versus Options Event Premium
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Official pre-event regulatory state improves risk-adjusted event-volatility pricing relative to a generic historical event move.
H0: the feasible `Historical absolute event returns grouped by market cap and indication` benchmark is not improved net of risk/cost.
Candidate: `Regulatory-document event taxonomy + shrinkage conditional jump model`. Advanced: Hierarchical Bayesian decision-state model and option-neutral density decomposition
Metrics: Jump variance calibration, option VRP after costs, event coverage, tail hedge error.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: ExpectedJumpVar_i=Σ_s p_{i,s}*(log(P_{after,s}/P_before))^2; VRP_i=ImpliedEventVar_i-ExpectedJumpVar_i-Cost_i.
- Units and payable/receivable cash direction from: s approval/rejection/delay states, p_s probabilities estimated strictly pre-decision; VRP is variance risk premium.
- True negative controls: FDA database daily updates can lag original approval; sample selection, delistings and halted option quotes.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** Conditional probability model fails event-matched calibration or net executable option premium..

## Cost and publication
Biotech option spreads and gap risk severe; define small budget and loss limit before evaluating.
$195k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$110k/$295k. Resulting 24m net ROI **-100.0% / -29.5% / 89.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
