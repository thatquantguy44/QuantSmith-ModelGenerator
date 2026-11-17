# Proposed runtime — ECB Collateral Eligibility-Cliff Prepositioning

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.ecb_eligibility` | rights-approved source manifest | typed ISIN x release version x effective date events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.ecb_eligibility_cliff_prepositioning.features` | snapshot | announced future eligibility matrix, haircut-adjusted coverage and replacement ladder |
| `qmg.research.ecb_eligibility_cliff_prepositioning.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.ecb_eligibility_cliff_prepositioning.candidate` | same inputs | dated replacement schedule and coverage stress certificate |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-02
mode: public_research
adapter: ecb_eligibility
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
python -m qmg.research.ecb_eligibility_cliff_prepositioning.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist dated replacement schedule and coverage stress certificate plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Preserve source byte hashes and schema versions; reject any unknown CHANGE code or missing effective date instead of guessing. Do not schedule this command until implementation and shadow gates pass.
