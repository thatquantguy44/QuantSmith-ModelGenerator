# Proposed runtime — Collateral Stale-Mark Quarantine and Conservative Valuation

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.collateral_marks` | rights-approved source manifest | typed collateral instrument x mark source x quote/receive event events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.collateral_stale_mark_quarantine.features` | snapshot | source age, price convention residual, lineage overlap and conservative interval |
| `qmg.research.collateral_stale_mark_quarantine.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.collateral_stale_mark_quarantine.candidate` | same inputs | mark status, safe monitoring valuation, lineage warning and escalation reason |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-06
mode: public_research
adapter: collateral_marks
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
python -m qmg.research.collateral_stale_mark_quarantine.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist mark status, safe monitoring valuation, lineage warning and escalation reason plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Target p99 <=100ms per 1,000-mark batch excluding upstream network; missing currency/convention hard-fails. Keep original marks immutable. Do not schedule this command until implementation and shadow gates pass.
