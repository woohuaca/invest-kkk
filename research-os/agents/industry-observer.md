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
6. 输出下一步动作：需要继续跟踪、更新洞察卡片，还是更新假设台账。

## 输出格式

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
- `signal.date`：信号日期，使用带引号日期。
- `signal.topic`：主题，使用 `policy / grid / power_market / storage / data_center / dispatch`。
- `signal.layer`：作用层级，使用 `generation / transmission / distribution / dispatch / EMS / VPP / operations_knowledge`。
- `signal.fact`：事实本身，不写推断。
- `strength`：`weak / medium / strong`。
- `confidence`：`low / medium / high`。
- `impact`：说明它可能影响哪个瓶颈、控制点、假设或评分维度。
- `next_action`：下一步动作。

## 示例

```yaml
signal:
  title: 容量市场改革提升稳定电源价值
  source: 电力市场政策更新
  source_url: https://www.ndrc.gov.cn/xxgk/jd/jd/202601/t20260130_1403521.html
  date: '2026-06-05'
  topic: power_market
  layer: dispatch
  fact: 市场规则开始更明确地为可靠容量和系统平衡能力定价。
strength: medium
confidence: medium
impact: 稳定容量和调度能力可能成为更重要的瓶颈。
next_action: 更新 `insights/` 相关洞察卡片，并在 `hypotheses/hypothesis-ledger.md` 跟踪容量市场落地证据。
```

## 输出落点

- weekly signal 写入 `data/collection-log.md`。
- 可比较指标写入或更新 `metrics/calculation-log.md`。
- 改变判断的信号写入 `insights/`。
- 验证或削弱假设的信号写入 `hypotheses/hypothesis-ledger.md`。

## 禁止事项

- 不从单条新闻直接推出买入或卖出建议。
- 不把政策口号当作已发生事实。
- 不把短期价格波动当作行业信号。
