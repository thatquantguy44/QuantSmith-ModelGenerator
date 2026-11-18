# Specification — Repo Compression with Cash-Flow Preservation

**QMG-20261116-01 · A — Securities finance · research design, empirical state BLOCKED.**

## Decision and hypothesis

Select existing tickets to tear up or resize without changing each participant's dated cash and CUSIP obligations. An economics-preserving compression reduces eligible gross ticket notional by at least 15% and operational cost by at least 10% versus bilateral pair cancellation, with no additional settlement or market risk.

```text
min_(x,z) sum_e a_e*x_e + k_e*z_e; A*x=A*q, D*x=D*q, 0<=x_e<=q_e, x_e<=M_e*z_e, z_e in {0,1}, x_e=lot_e*m_e, m_e integer
```

e indexes consenting tickets within the same legally approved set; q and x are original and retained face amounts; A maps tickets to dated participant/CUSIP flows; D maps them to dated cash flows including accrued repo interest; a is gross-capacity cost per face dollar; k is per-ticket cost; z marks retained tickets; M=q; lot is the permitted denomination.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-01-REQ-01 | Ingest repo ticket and dated cash/security obligation | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-01-REQ-02 | Build dated incidence matrices, lot constraints and consent mask | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-01-REQ-03 | Implement baseline: Cancel exact opposite tickets bilaterally within a legal set; otherwise hold the original book. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-01-REQ-04 | Fit/solve Mixed-integer minimum-cost circulation with exact cash-flow conservation | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-01-REQ-05 | Evaluate retained gross notional and verified per-date cash/security conservation | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-01-REQ-06 | Produce proposed tear-up/resizing schedule, exact flow certificate and rejected-action reasons | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-01-NFR-01 | For a proposed 5,000-ticket set, target p95 solve time <=60 seconds and exact conservation certificate; infeasible or timed-out solves return original book. |
| QMG-20261116-01-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-01-AC-01 | GO only with >=15% gross reduction and >=10% realized operational cost reduction on held-out eligible sets; every cash/security residual <=$0.01 cash or zero security units; zero consent violations. STOP on any economic transfer or if gains vanish after legal filtering. |
| QMG-20261116-01-AC-02 | Construct a three-node cycle with mismatched maturity dates: it must remain uncompressed; changing one consent flag must remove every affected action. |
| QMG-20261116-01-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Ticket ID, legal-set ID, participant pseudonym, CUSIP, start/end timestamps, cash principal, accrued interest, rate convention, face amount, consent flag and minimum lot. Public rules plus synthetic networks first; public aggregates cannot reconstruct a private trade graph. Clock: Freeze the ledger at 14:00 America/New_York; use only confirmed records ingested by 13:55 and decisions before the relevant service cutoff. Cash-flow amendments received later enter the next solve. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Legal netting is not created by algebra; different dates, rates and counterparties must not be silently offset. Synthetic network density can overstate capacity. Illustrative $1bn eligible matched book; no directional risk capital assumed. Economics come from fewer messages and approved gross-capacity charges, not treating all removed notional as regulatory capital relief. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: Medium: constrained compression with dated multi-asset conservation; novelty relative to existing compression literature needs a dedicated review.
