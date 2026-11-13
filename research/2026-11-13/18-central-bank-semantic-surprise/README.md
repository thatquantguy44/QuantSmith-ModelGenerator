# Central-Bank Communication Semantic Surprise Across Languages
**B · Domestic & global markets** · **Priority 88/100** · **Difficulty High** · **Feasibility: Medium-high on official statements** · **Publication interest 5/5 (conceptual, not a paper).**

## Why this exists
Translated central-bank statements can obscure a policy stance change; narrative models can also contaminate price signals with post-event commentary.

**Market / geography:** US Federal Reserve, ECB and selected Asian monetary authorities. **Asset classes:** G10 FX, rates and equity index futures.

## Falsifiable hypothesis and investment/operational decision
Claim-grounded semantic stance revisions add stable information beyond rate decision and scheduled policy surprise alone across languages.

**Decision:** Quantify official policy-message *differences* between successive statements to adjust next-session FX/rates exposure..

## Research model
```text
Surprise_t = SentenceDistance(text_t, text_(t-1)) - ExpectedShift_t; alpha_(t+1)=β*Surprise_t, with abstention on low translation confidence
```
text_t is official published statement as of event; ExpectedShift requires pre-event expectations and is omitted if unavailable rather than inferred ex post.

## Data and decision clock
Versioned official policy statements; actual publication timestamps; pre-event interest rate futures; FX and rates price bars; translated text audit. **Observation grain:** central-bank event × original language × statement version × publication timestamp. **Decision horizon:** after official statement becomes public; never permit news articles, transcripts or price reactions from after decision in input.

## Baseline versus candidate
- **Baseline:** Policy rate surprise (or no-surprise dummy without licensed expectation) and prior-day rate changes.
- **Proposed model:** Source-grounded claim-difference extractor with multilingual uncertainty and simple linear evaluation.
- **Advanced option:** Constrained multilingual textual event state-space with calibration and abstention threshold.
- **Primary metrics:** out-of-sample price direction log loss, FX hedge information ratio, translation agreement and unsupported claim rate.
- **Falsification:** Reject if no incremental holdout log-loss improvement or semantic extractor makes unsupported claims on challenge set.
- **Primary economic or methodological caveat:** Translation distortions, backfilled statement updates, and post-event news leakage are especially severe for multilingual event models.

## 24-month ROI sensitivity (unverified assumptions only)
USD $160k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$320k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 100%**. NOT forecast or historical measurement. Economic lever: hypothetical $10m liquid G10 hedge sleeve with up to 160 bps 2-year value if statistically robust; zero benefit plausible.

## Execution, capacity and feasibility
Only next-session liquid FX/rates futures; policy event size, slippage and gap risk explicitly costed.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
