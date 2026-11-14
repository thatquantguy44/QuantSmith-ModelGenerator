# EVALS — Cross-Book Securities Finance Identity Reconciliation Graph
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** A provenance-aware deterministic graph matcher reduces unresolved break hours and false exposure duplications compared with fuzzy string matching.
- **Comparator:** Exact ID join plus manually triaged fuzzy-name matches..
- **Candidate:** Bipartite deterministic matching with hard identity constraints and provenance..
- **Advanced alternative:** Human-review active-learning on uncertain clusters with error budget and privacy-preserving synthetic tests..
- **Metrics:** false merge rate, unmatched %, time to resolve, duplicate exposure USD, manual review hours..
- **Stop/no-go:** Reject if critical false merges exceed zero in labeled holdouts or operations time does not decline.
- **Cost sensitivity:** USD $145k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $60k–$295k over 24 months. Net ROI = (gross benefit − cost)/cost = **-59% to 103%**. NOT forecast or historical measurement. Economic lever: scenario: 100–500 manual breaks annually at assumed fully loaded remediation costs; purely hypothetical.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. real-time/overnight reconciliation; no future correction can be applied retroactively to a prior risk snapshot
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: No market capacity required; scalability measured in records/day and audit/log cost, not claimed P&L.
7. Stress identification risk: LLM or probabilistic model can silently merge legally distinct entities or settlement legs.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
no cross-entity false merge; amendment chain; currency normalization; ID recycling and lifecycle updates.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
