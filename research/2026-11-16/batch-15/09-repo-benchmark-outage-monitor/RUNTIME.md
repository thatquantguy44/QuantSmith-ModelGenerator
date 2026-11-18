# Proposed runtime — Repo Benchmark Outage and Revision Risk Monitor

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.repo_publication_events` | rights-approved source manifest | typed reference rate x publication event x revision version events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.repo_benchmark_outage_monitor.features` | snapshot | rate release age, version chain, contingency flag and interval width |
| `qmg.research.repo_benchmark_outage_monitor.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.repo_benchmark_outage_monitor.candidate` | same inputs | accept/interval/review status, immutable as-of report and official-source pointer |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-09
mode: public_research
adapter: repo_publication_events
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
python -m qmg.research.repo_benchmark_outage_monitor.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist accept/interval/review status, immutable as-of report and official-source pointer plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Append-only publication ledger; fail closed on missing source/version and keep synthetic monitoring estimates in a separate schema. Do not schedule this command until implementation and shadow gates pass.
