# Weekly Signal Schema

## 结论

Weekly signal 是数据采集层的最小输出单位。它记录事实、信号强度、置信度、影响和下一步动作。

## Schema

```yaml
signal:
  title:
  source:
  date:
  topic:
  layer:
  fact:
strength:
confidence:
impact:
next_action:
```

## 字段说明

- `signal.title`：一句话信号标题。
- `signal.source`：信息来源。
- `signal.date`：事实日期或发布日期。
- `signal.topic`：`policy / grid / power_market / storage / data_center / dispatch`。
- `signal.layer`：`generation / transmission / distribution / dispatch / EMS / VPP / operations_knowledge`。
- `signal.fact`：事实本身，不写推断。
- `strength`：`weak / medium / strong`。
- `confidence`：`low / medium / high` 或百分比。
- `impact`：该事实可能影响的瓶颈、控制点、指标或假设。
- `next_action`：下一步进入 `metrics/`、`insights/`、`hypotheses/` 或 `control-rights/`。

## 示例

```yaml
signal:
  title: Dispatch reform increases value of stable capacity
  source: Power market reform document
  date: 2026-06-05
  topic: power_market
  layer: dispatch
  fact: Market rules increasingly price reliability and balancing capacity.
strength: medium
confidence: medium
impact: Stable capacity and dispatch capability may become more visible control points.
next_action: Update metrics/power-layer-metrics.md and insights/examples/stable-capacity-becomes-scarce.md.
```
