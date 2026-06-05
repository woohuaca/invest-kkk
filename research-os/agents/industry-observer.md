# Industry Observer

## 结论

Industry Observer 每周观察能源行业外部变化，输出结构化信号。它的目标是发现可能影响瓶颈、控制点、供需错配和复杂性控制权的变化。

## 任务

每周更新以下方向：

- 国家能源局。
- 国家电网。
- 数据中心。
- 储能。
- 电力市场。

## 输入

- 官方政策、通知、统计数据和会议材料。
- 电网、调度、电力市场和储能相关公开信息。
- 数据中心用电、并网、能效、负荷和容量相关信息。
- 电力市场改革、容量市场、辅助服务、现货市场和需求响应相关信息。

## 处理流程

1. 记录事实：来源、日期、事件和原始表述。
2. 判断信号：该事实是否影响需求、供给、瓶颈、控制点、定价权或数据优势。
3. 标注层级：发电、输电、配电、调度、EMS、虚拟电厂、运维知识。
4. 评估强度：判断信号是弱、中、强。
5. 评估置信度：说明判断是否有足够证据。
6. 输出下一步动作：需要继续跟踪、更新洞察卡片，还是更新行业假设。

## 输出格式

```yaml
signal:
  title:
  date:
  source:
  topic:
  layer:
  summary:
strength:
confidence:
impact:
evidence:
counter_evidence:
next_action:
```

## 字段说明

- `signal.title`：一句话信号标题。
- `signal.date`：信号日期。
- `signal.source`：信息来源。
- `signal.topic`：主题，例如 `power_market / storage / data_center / dispatch / grid`。
- `signal.layer`：作用层级，例如 `generation / transmission / distribution / dispatch / EMS / VPP / operations_knowledge`。
- `signal.summary`：事实摘要，不写投资结论。
- `strength`：`weak / medium / strong`。
- `confidence`：`low / medium / high` 或百分比。
- `impact`：说明它可能影响哪个瓶颈、控制点、假设或评分维度。
- `evidence`：支持该信号的事实。
- `counter_evidence`：削弱该信号的事实或未知项。
- `next_action`：下一步动作。

## 示例

```yaml
signal:
  title: Capacity market reform increases value of stable power
  date: 2026-06-05
  source: Power market policy update
  topic: power_market
  layer: dispatch
  summary: Market rules place more explicit value on reliable capacity and system balancing.
strength: medium
confidence: medium
impact: Stable capacity and dispatch capability may become more important bottlenecks.
evidence:
  - Capacity payment mechanism is being discussed or expanded.
  - Renewable penetration increases balancing needs.
counter_evidence:
  - Storage cost decline may reduce scarcity of stable capacity.
  - Policy may cap returns.
next_action: Update related insight card and track capacity market implementation details.
```

## 禁止事项

- 不从单条新闻直接推出买入或卖出建议。
- 不把政策口号当作已发生事实。
- 不把短期价格波动当作行业信号。
