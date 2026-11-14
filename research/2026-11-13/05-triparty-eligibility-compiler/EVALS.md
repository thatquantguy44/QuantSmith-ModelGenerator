# EVALS — Tri-Party Collateral Eligibility Clause-to-Constraint Compiler
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** A dual-path deterministic parser plus LLM reviewer reduces incorrect collateral acceptances versus manually transcribed spreadsheets.
- **Comparator:** Rule tables hand-transcribed and checked by two human operators..
- **Candidate:** Schema-constrained text extraction with symbolic eligibility evaluation and abstention..
- **Advanced alternative:** Contradiction-aware graph of rule amendments with formal test generation and reviewer feedback..
- **Metrics:** false eligibility acceptance rate, false rejection rate, review labor, coverage, abstention, parse latency..
- **Stop/no-go:** Reject if any critical false acceptance appears in stress fixtures or human review burden fails to improve.
- **Cost sensitivity:** USD $220k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $95k–$365k over 24 months. Net ROI = (gross benefit − cost)/cost = **-57% to 66%**. NOT forecast or historical measurement. Economic lever: estimated 200–600 hours of manual eligibility review and avoided hypothetical exception remediations; unverified.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. rules valid at collateral decision; amendments apply from legal effective date, not document creation date
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Can serve as quality-gate software without trading access; execution requires approved legal rules and certified contracts.
7. Stress identification risk: Natural-language ambiguity, contract precedence and jurisdiction-specific clauses make full automation unsafe.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
ambiguous clause abstention; amendments supersede rules; unsupported security rejected; contradiction quarantine.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
