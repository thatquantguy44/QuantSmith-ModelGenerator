# Proposed runtime — US Municipal Call-Exercise Friction Surface

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.muni_call_disclosures` | rights-approved source manifest | typed bond x call opportunity x public notice/financial filing event events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.us_muni_call_exercise_friction.features` | snapshot | refunding incentive, notice state, issuer friction and time-to-call |
| `qmg.research.us_muni_call_exercise_friction.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.us_muni_call_exercise_friction.candidate` | same inputs | call probability surface, cash-flow distribution and duration-matched selection report |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-15
mode: public_research
adapter: muni_call_disclosures
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
python -m qmg.research.us_muni_call_exercise_friction.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist call probability surface, cash-flow distribution and duration-matched selection report plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Every parsed call term needs a document page/span; conflicting extraordinary versus optional redemption clauses block valuation. Do not schedule this command until implementation and shadow gates pass.
