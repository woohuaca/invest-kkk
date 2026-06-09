# Weekly Signal Schema

## 结论

Weekly signal 是数据采集层的最小输出单位。它记录事实、信号强度、置信度、影响和下一步动作。

## Schema

```yaml
signal:
  title:
  source:
  source_url:
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
- `signal.source_url`：来源链接，优先使用官方原文或可追溯公开报道。
- `signal.date`：事实日期或发布日期。
- `signal.topic`：`policy / grid / power_market / storage / data_center / dispatch`。
- `signal.layer`：`generation / transmission / distribution / dispatch / EMS / VPP / operations_knowledge`。
- `signal.fact`：事实本身，不写推断。
- `strength`：`weak / medium / strong`。
- `confidence`：`low / medium / high`。
- `impact`：该事实可能影响的瓶颈、控制点、指标或假设。
- `next_action`：下一步进入 `metrics/`、`insights/`、`hypotheses/` 或 `control-rights/`。

## 示例

```yaml
signal:
  title: 调度改革提升稳定容量价值
  source: 电力市场改革文件
  source_url: https://www.ndrc.gov.cn/xxgk/jd/jd/202601/t20260130_1403521.html
  date: '2026-06-05'
  topic: power_market
  layer: dispatch
  fact: 市场规则开始更明确地为可靠性和调节能力定价。
strength: medium
confidence: medium
impact: 稳定容量和调度能力可能成为更可见的控制点。
next_action: 更新 metrics/power-layer-metrics.md 和 insights/examples/stable-capacity-becomes-scarce.md。
```
