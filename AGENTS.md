# QuantSmith-ModelGenerator — Agent instructions
**Mission:** Public, reproducible 20-idea research planning with **10 securities-finance** and **10 domestic/global quant-market** ideas per scheduled batch. Existing 15-idea historical batches remain untouched.

## Authority and publication constraints
- Agents draft hypotheses, model specifications, synthetic tests, source/claim ledgers and agent contracts; they cannot trade, grant data access, certify legal clauses, deploy software or auto-merge pull requests.
- Never commit employer systems, real client positions, counterparties, nonpublic data, secrets, unlicensed vendor extracts, restricted papers or proprietary code to this public repository.
- Every market datum must be attached to `observed_at`, `published_at`, `available_at`, its source/version and legal license category. Disallow using an observation before its public dissemination.
- Paper links are background theory, **not empirical confirmation** of new research hypotheses. Current sources are official portals, with differing licenses and missing values.
- Each idea needs testable REQ/NFR/AC, baseline, advanced alternative, falsification, a credible cost/capacity model, quantitative *illustrative-only* net ROI, and negative-test plan.
- Proposed `AGENT.md`, `SKILL.md`, `PROMPT.md`, `TOOLING.md`, `WORKFLOW.md`, `RUNTIME.md`, `EVALS.md` are documentation until implemented and verified.
- For each batch create one date-scoped branch and one **draft** PR, not twenty individual PRs. Verify changed file count. No automatic merge.
- Preserve all historical batches verbatim; if a shared guide changes, ensure it does not change older research evidence/status.

## Review gates
1. Novelty compared with existing archive.
2. License and public/private data boundary.
3. Correct unit economics and point-in-time availability.
4. Independent baseline and falsifiable acceptance criteria.
5. Synthetic fixtures and negative tests.
6. No unsupported empirical claims.
7. Human review before any market trading or deployment.
