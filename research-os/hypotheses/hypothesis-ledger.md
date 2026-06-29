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
last_updated: '2026-06-29'
previous_confidence: 75%
confidence_change_reason: 1-5月风光装机继续高增且发电设备利用小时下降，增强稳定容量和调度复杂性证据；但2030年储能、VPP、车网互动和需求侧调节目标，以及充电设施高增，也增强灵活性供给反证，因此置信度暂不调整。
supporting_evidence:
  - 新能源渗透率提升会增加系统平衡复杂性。
  - 电力市场改革可能让可靠性价值更显性。
  - 2026年1-4月太阳能和风电装机继续高增，但全国发电设备平均利用小时同比下降。
  - 发电侧容量电价机制开始覆盖煤电、气电、抽水蓄能和新型储能。
  - 2026 年部分电池材料价格出现回升迹象，提示上游资源端可能重新影响储能扩张速度。
  - 2026年1-4月全国可再生能源装机突破24亿千瓦，占全国电力总装机60.5%。
  - 截至2026年5月底，全国累计发电装机容量40.1亿千瓦，其中太阳能发电装机12.7亿千瓦、风电6.6亿千瓦，风光继续高增。
  - 2026年1-5月全国发电设备累计平均利用1155小时，同比降低95小时。
counter_evidence:
  - 储能成本可能快速下降。
  - 需求响应可能降低稳定容量稀缺性。
  - 储能市场化推进可能提高调节资源利用率，削弱稳定容量稀缺。
  - 锂、钴、镍、天然石墨价格已从高峰回落，可能继续支持储能降本和供给扩张。
  - 截至2025年底全国新型储能装机规模达到1.36亿千瓦/3.51亿千瓦时，虚拟电厂和车网互动聚合资源也在扩大。
  - 新型能源体系试点申报文件提出到2030年新型储能装机3亿千瓦以上、虚拟电厂容量5000万千瓦以上、车网互动响应能力5000万千瓦以上。
  - 充电设施数量、公共充电功率、私人接入容量和充放电电量继续高增，可能提高需求侧灵活性供给。
linked_insights:
  - insights/examples/stable-capacity-becomes-scarce.md
linked_metrics:
  - renewable_penetration
  - capacity_utilization
  - peak_valley_spread
  - dispatch_market_reform
  - storage_utilization
  - charging_load_growth
  - battery_material_price_index
  - storage_cost_pressure
  - resource_cycle_rebound
next_action: 跟踪迎峰度夏负荷、容量补偿机制、储能/VPP实际调用收益、车网互动响应能力和峰时价差。
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
last_updated: '2026-06-29'
previous_confidence: 70%
confidence_change_reason: 新型能源体系试点继续把源网荷储协同、需求侧调节、VPP和车网互动纳入2030年目标，增强调度层方向性证据；但本周缺少新的实际交易深度和商业化收益数据，因此置信度暂不调整。
supporting_evidence:
  - 分布式发电和灵活负荷会提高系统复杂性。
  - 发电侧容量电价机制推动可靠容量和顶峰能力显性定价。
  - 算力设施被鼓励作为负荷侧灵活可调节资源参与电网运行。
  - 省级电力现货市场实现基本全覆盖，多个省份推动实时市场5分钟出清。
  - 云霄直流启动输电权市场化交易，跨区通道和网间互济开始更明确地进入市场化机制。
  - 新型能源体系试点提出源网荷储协调互济资源配置能力较2025年提升40%以上，需求侧调节能力达到最大用电负荷5%以上。
counter_evidence:
  - 电网运营方或监管主体可能限制调度价值的商业化获取。
  - 市场正式运行比例、交易深度、辅助服务收益和价格波动仍需持续验证。
  - 2030年政策目标不等于当前实际调度收益和商业化可获得性。
linked_insights: []
linked_metrics:
  - dispatch_market_reform
  - peak_valley_spread
  - day_ahead_realtime_spread
  - congestion
  - demand_response
next_action: 跟踪 2026 年一半以上省份电力现货市场正式运行、辅助服务市场推进、跨经营区交易常态化和需求响应实际调用。
```

## Hypothesis: energy-003

```yaml
hypothesis:
  id: energy-003
  title: EMS Value Depends on Organizational Dependency
  statement: EMS 和 VPP 的价值取决于组织依赖，而不只是聚合容量。
  scope: Control Point / Company
status: active
confidence: 65%
last_updated: '2026-06-29'
previous_confidence: 60%
confidence_change_reason: 充电设施高增、2030年VPP和车网互动目标、绿证与非化石能源电力消费核算衔接，开始提供从资源聚合走向企业工作流的证据；但实际调用收益和客户切换成本仍未验证，因此只小幅上调。
supporting_evidence:
  - 分布式资产增长后，客户更难用人工方式管理能源系统。
  - 互联网数据服务用电快速增长，提高高可靠负荷管理需求。
  - 算电协同行动方案鼓励算力设施参与电网运行。
  - 虚拟电厂理论调节能力超过1600万千瓦，车网互动聚合资源超过1900万千瓦。
  - 全国充电设施数量、公共充电功率、私人接入容量和充放电电量继续高增，提高配网、车网互动和客户侧能源管理复杂性。
  - 绿证交易与非化石能源电力消费责任权重衔接，可能把绿电采购、合规核算和用电数据纳入企业常态工作流。
counter_evidence:
  - 如果客户切换成本保持较低，EMS 可能商品化。
  - 理论调节能力不等于实际调用能力、客户依赖或收益稳定性。
  - 绿证核算可能停留在合规报送层面，不一定形成高频 EMS 使用或平台控制权。
linked_insights: []
linked_metrics:
  - data_center_load_growth
  - demand_response
  - charging_load_growth
  - storage_utilization
  - green_power_accounting
  - market_volatility
  - customer_switching_cost
  - data_feedback_loop
next_action: 寻找企业绿电核算工作流、数据中心客户依赖、需求响应履约、VPP实际调用收益和数据反馈证据。
```
