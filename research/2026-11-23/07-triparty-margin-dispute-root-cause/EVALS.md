# EVALS — Tri-Party Repo Margin Dispute Root-Cause and Evidence Classifier
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: A deterministic calculation engine plus provenance graph resolves more disputes correctly than keyword-based ticket routing.
H0: the feasible `FIFO triage by dispute amount and ticket keywords` benchmark is not improved net of risk/cost.
Candidate: `Deterministic valuation reconciliation then provenance-based root-cause ranking`. Advanced: Constrained language-model document extraction with deterministic verifier and abstain-on-conflict
Metrics: Seeded root-cause accuracy, false escalations, time-to-resolution, unresolved material exposure.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: DisputeAmount_j=Σ_i (Mark_{i,t}*(1-h_i)*Qty_i)_bank - Σ_i (Mark_{i,t}*(1-h_i)*Qty_i)_agent.
- Units and payable/receivable cash direction from: h_i haircut and Mark_i mark at contractual timestamp; compare sides only when valuation basis matches.
- True negative controls: Conflicting vendor marks, jurisdiction-specific terms, privacy and LLM overconfidence.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** LLM cannot improve verified resolver without hallucinated legal clauses or unacceptable false settlements..

## Cost and publication
Operational capacity limited by manual reviewer; never auto-settle margin on agent output.
$145k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$110k/$205k. Resulting 24m net ROI **-100.0% / 13.8% / 112.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
