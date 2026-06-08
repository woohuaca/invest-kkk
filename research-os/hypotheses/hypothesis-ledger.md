# 假设台账

## 结论

本文件记录 Energy Research OS v0.1 的核心假设。每条假设必须包含状态、置信度、更新日期、置信度变化原因、证据、反证和下一步动作。

## Hypothesis: energy-001

```yaml
hypothesis:
  id: energy-001
  title: Stable Capacity Becomes Scarce
  statement: 稳定电力容量会随着新能源渗透率提升而变得更有系统价值。
  scope: Bottleneck / Control Point
status: active
confidence: 70%
last_updated: '2026-06-05'
previous_confidence: null
confidence_change_reason: 初始记录，尚无历史置信度变化。
supporting_evidence:
  - 新能源渗透率提升会增加系统平衡复杂性。
  - 电力市场改革可能让可靠性价值更显性。
counter_evidence:
  - 储能成本可能快速下降。
  - 需求响应可能降低稳定容量稀缺性。
linked_insights:
  - insights/examples/stable-capacity-becomes-scarce.md
linked_metrics:
  - renewable_penetration
  - capacity_utilization
  - peak_valley_spread
next_action: 跟踪调度市场改革和储能利用率。
```

## Hypothesis: energy-002

```yaml
hypothesis:
  id: energy-002
  title: Dispatch Layer Gains Complexity Control
  statement: 调度层可能比单一发电资产获得更长期的复杂性控制权。
  scope: Control Point
status: active
confidence: 60%
last_updated: '2026-06-05'
previous_confidence: null
confidence_change_reason: 初始记录，尚无历史置信度变化。
supporting_evidence:
  - 分布式发电和灵活负荷会提高系统复杂性。
counter_evidence:
  - 电网运营方或监管主体可能限制调度价值的商业化获取。
linked_insights: []
linked_metrics:
  - dispatch_market_reform
  - peak_valley_spread
next_action: 比较 dispatch、EMS 和 VPP 的控制权层级。
```

## Hypothesis: energy-003

```yaml
hypothesis:
  id: energy-003
  title: EMS Value Depends on Organizational Dependency
  statement: EMS 和 VPP 的价值取决于组织依赖，而不只是聚合容量。
  scope: Control Point / Company
status: active
confidence: 60%
last_updated: '2026-06-05'
previous_confidence: null
confidence_change_reason: 初始记录，尚无历史置信度变化。
supporting_evidence:
  - 分布式资产增长后，客户更难用人工方式管理能源系统。
counter_evidence:
  - 如果客户切换成本保持较低，EMS 可能商品化。
linked_insights: []
linked_metrics:
  - customer_switching_cost
  - data_feedback_loop
next_action: 寻找 EMS 客户工作流依赖和数据反馈证据。
```
