# Proposed runtime — Japan Buyback Completion Credibility

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.japan_buyback_filings` | rights-approved source manifest | typed issuer x announced buyback program x filing acceptance event events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.japan_buyback_completion_credibility.features` | snapshot | prior completion rate, cash-funded capacity, expiry horizon and free-float-normalized authorization |
| `qmg.research.japan_buyback_completion_credibility.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.japan_buyback_completion_credibility.candidate` | same inputs | completion probabilities and neutral event-sleeve research orders |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-11
mode: public_research
adapter: japan_buyback_filings
as_of_utc: REQUIRED_FROM_RUN
source_manifest: REQUIRED_REVIEWED_PATH_AND_HASH
cost_config: REQUIRED_MEASURED_OR_LABELED_SCENARIO
limits: REQUIRED_DOMAIN_APPROVED_LIMITS
seed: 20261116
allow_private_inputs: false
allow_live_orders: false
```

Illustrative **future** command, expected to fail today because no runtime exists:

```bash
python -m qmg.research.japan_buyback_completion_credibility.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist completion probabilities and neutral event-sleeve research orders plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Retain Japanese original text, accession ID and extraction span; any translation/model extraction without supporting span is excluded. Do not schedule this command until implementation and shadow gates pass.
