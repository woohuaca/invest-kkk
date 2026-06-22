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
last_updated: '2026-06-22'
previous_confidence: 75%
confidence_change_reason: 可再生能源装机和市场机制继续增强稳定容量稀缺证据，但新型储能、虚拟电厂和车网互动聚合资源规模同步扩大，供给弹性反证也增强，因此置信度暂不调整。
supporting_evidence:
  - 新能源渗透率提升会增加系统平衡复杂性。
  - 电力市场改革可能让可靠性价值更显性。
  - 2026年1-4月太阳能和风电装机继续高增，但全国发电设备平均利用小时同比下降。
  - 发电侧容量电价机制开始覆盖煤电、气电、抽水蓄能和新型储能。
  - 2026 年部分电池材料价格出现回升迹象，提示上游资源端可能重新影响储能扩张速度。
  - 2026年1-4月全国可再生能源装机突破24亿千瓦，占全国电力总装机60.5%。
counter_evidence:
  - 储能成本可能快速下降。
  - 需求响应可能降低稳定容量稀缺性。
  - 储能市场化推进可能提高调节资源利用率，削弱稳定容量稀缺。
  - 锂、钴、镍、天然石墨价格已从高峰回落，可能继续支持储能降本和供给扩张。
  - 截至2025年底全国新型储能装机规模达到1.36亿千瓦/3.51亿千瓦时，虚拟电厂和车网互动聚合资源也在扩大。
linked_insights:
  - insights/examples/stable-capacity-becomes-scarce.md
linked_metrics:
  - renewable_penetration
  - capacity_utilization
  - peak_valley_spread
  - dispatch_market_reform
  - storage_utilization
  - battery_material_price_index
  - storage_cost_pressure
  - resource_cycle_rebound
next_action: 跟踪容量补偿机制、储能利用率、峰时价差和电池材料价格是否持续回升。
```

## Hypothesis: energy-002

```yaml
hypothesis:
  id: energy-002
  title: Dispatch Layer Gains Complexity Control
  statement: 调度层可能比单一发电资产获得更长期的复杂性控制权。
  scope: Control Point
status: active
confidence: 70%
last_updated: '2026-06-22'
previous_confidence: 65%
confidence_change_reason: 省级电力现货市场基本全覆盖、实时市场5分钟出清扩围、跨经营区交易和输电权市场化交易推进，调度层复杂性控制权证据增强。
supporting_evidence:
  - 分布式发电和灵活负荷会提高系统复杂性。
  - 发电侧容量电价机制推动可靠容量和顶峰能力显性定价。
  - 算力设施被鼓励作为负荷侧灵活可调节资源参与电网运行。
  - 省级电力现货市场实现基本全覆盖，多个省份推动实时市场5分钟出清。
  - 云霄直流启动输电权市场化交易，跨区通道和网间互济开始更明确地进入市场化机制。
counter_evidence:
  - 电网运营方或监管主体可能限制调度价值的商业化获取。
  - 市场正式运行比例、交易深度、辅助服务收益和价格波动仍需持续验证。
linked_insights: []
linked_metrics:
  - dispatch_market_reform
  - peak_valley_spread
  - day_ahead_realtime_spread
  - congestion
  - demand_response
next_action: 跟踪 2026 年一半以上省份电力现货市场正式运行、辅助服务市场推进和跨经营区交易常态化。
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
last_updated: '2026-06-22'
previous_confidence: 60%
confidence_change_reason: 虚拟电厂理论调节能力和车网互动聚合资源扩大，支持 EMS/VPP 的资源聚合价值；但仍缺少客户工作流依赖、实际调用收益和切换成本证据，因此维持置信度。
supporting_evidence:
  - 分布式资产增长后，客户更难用人工方式管理能源系统。
  - 互联网数据服务用电快速增长，提高高可靠负荷管理需求。
  - 算电协同行动方案鼓励算力设施参与电网运行。
  - 虚拟电厂理论调节能力超过1600万千瓦，车网互动聚合资源超过1900万千瓦。
counter_evidence:
  - 如果客户切换成本保持较低，EMS 可能商品化。
  - 理论调节能力不等于实际调用能力、客户依赖或收益稳定性。
linked_insights: []
linked_metrics:
  - data_center_load_growth
  - demand_response
  - storage_utilization
  - market_volatility
  - customer_switching_cost
  - data_feedback_loop
next_action: 寻找数据中心客户工作流依赖、需求响应履约、VPP实际调用收益和数据反馈证据。
```
