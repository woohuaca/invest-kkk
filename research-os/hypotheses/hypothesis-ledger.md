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
confidence: 75%
last_updated: '2026-06-09'
previous_confidence: 70%
confidence_change_reason: 风光装机高增、利用小时下降和发电侧容量电价机制共同增强稳定容量稀缺与可靠容量显性定价证据。
supporting_evidence:
  - 新能源渗透率提升会增加系统平衡复杂性。
  - 电力市场改革可能让可靠性价值更显性。
  - 2026年1-4月太阳能和风电装机继续高增，但全国发电设备平均利用小时同比下降。
  - 发电侧容量电价机制开始覆盖煤电、气电、抽水蓄能和新型储能。
counter_evidence:
  - 储能成本可能快速下降。
  - 需求响应可能降低稳定容量稀缺性。
  - 储能市场化推进可能提高调节资源利用率，削弱稳定容量稀缺。
linked_insights:
  - insights/examples/stable-capacity-becomes-scarce.md
linked_metrics:
  - renewable_penetration
  - capacity_utilization
  - peak_valley_spread
  - dispatch_market_reform
  - storage_utilization
next_action: 跟踪容量补偿机制、储能利用率和峰时价差。
```

## Hypothesis: energy-002

```yaml
hypothesis:
  id: energy-002
  title: Dispatch Layer Gains Complexity Control
  statement: 调度层可能比单一发电资产获得更长期的复杂性控制权。
  scope: Control Point
status: active
confidence: 65%
last_updated: '2026-06-09'
previous_confidence: 60%
confidence_change_reason: 容量电价机制和算电协同行动方案都把系统平衡、顶峰能力和负荷灵活性推向调度层，调度复杂性控制权证据增强。
supporting_evidence:
  - 分布式发电和灵活负荷会提高系统复杂性。
  - 发电侧容量电价机制推动可靠容量和顶峰能力显性定价。
  - 算力设施被鼓励作为负荷侧灵活可调节资源参与电网运行。
counter_evidence:
  - 电网运营方或监管主体可能限制调度价值的商业化获取。
linked_insights: []
linked_metrics:
  - dispatch_market_reform
  - peak_valley_spread
  - demand_response
next_action: 比较 dispatch、EMS、VPP 和算电协同的控制权层级。
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
last_updated: '2026-06-09'
previous_confidence: 60%
confidence_change_reason: 互联网数据服务用电高增和算电协同政策支持 EMS/VPP 价值，但尚缺客户工作流依赖和切换成本证据，因此维持置信度。
supporting_evidence:
  - 分布式资产增长后，客户更难用人工方式管理能源系统。
  - 互联网数据服务用电快速增长，提高高可靠负荷管理需求。
  - 算电协同行动方案鼓励算力设施参与电网运行。
counter_evidence:
  - 如果客户切换成本保持较低，EMS 可能商品化。
linked_insights: []
linked_metrics:
  - data_center_load_growth
  - demand_response
  - customer_switching_cost
  - data_feedback_loop
next_action: 寻找数据中心客户工作流依赖、需求响应履约和数据反馈证据。
```
