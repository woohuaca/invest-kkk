# 控制点候选

## 结论

本文件记录未来 10 年电力产业控制权候选。候选不是股票推荐，而是需要继续研究的控制点和资产类型。

## Candidate: dispatch-layer

```yaml
candidate:
  layer: dispatch
  asset_type: 市场与系统平衡能力
  control_point: 调度层可能控制发电、储能、负荷和市场规则之间的实时复杂性。
score:
  complexity_control: 5
  bottleneck_power: 4
  pricing_power: 3
  data_advantage: 4
  organizational_dependency: 3
  supply_response_lag: 4
  durability: 4
evidence:
  - 新能源渗透率提升会增加系统平衡复杂性。
  - 电力市场改革可能为可靠性和灵活性定价。
  - 发电侧容量电价机制开始覆盖煤电、气电、抽水蓄能和新型储能。
  - 重点省份现货价格分化和日前-实时价差提示调度、预测和实时平衡的重要性上升。
counter_evidence:
  - 监管主体或电网运营方可能吸收大部分价值。
  - 市场改革推进可能较慢。
confidence: medium
next_action: 跟踪调度市场改革，并链接到 `metrics/metric-catalog.md`。
```

## Candidate: EMS

```yaml
candidate:
  layer: EMS
  asset_type: 企业能源管理操作层
  control_point: EMS 可能成为分布式发电、储能、充电和灵活负荷的企业操作层。
score:
  complexity_control: 4
  bottleneck_power: 3
  pricing_power: 3
  data_advantage: 4
  organizational_dependency: 5
  supply_response_lag: 3
  durability: 4
evidence:
  - 客户需要同时管理能源成本、可靠性和合规要求。
  - 工作流集成可能提高客户切换成本。
  - 数据中心高可靠负荷增长和算电协同政策提高能源管理复杂度。
  - 省级现货价格波动会提高客户侧能源成本优化、负荷调整和储能协同需求。
counter_evidence:
  - 如果切换成本保持较低，EMS 可能商品化。
  - 公用事业公司或电网运营方可能控制调度入口。
confidence: medium
next_action: 寻找数据中心客户依赖、需求响应履约和数据反馈证据。
```

## Candidate: compute-power-coordination

```yaml
candidate:
  layer: EMS
  asset_type: 算电协同操作与调度层
  control_point: 算电协同可能把数据中心负荷、绿电消纳、需求响应和电力价格信号连接成新的控制层。
score:
  complexity_control: 4
  bottleneck_power: 3
  pricing_power: 3
  data_advantage: 4
  organizational_dependency: 4
  supply_response_lag: 3
  durability: 4
evidence:
  - 互联网数据服务用电保持高增，提高高可靠负荷管理需求。
  - 算电协同行动方案鼓励算力设施作为负荷侧灵活可调节资源参与电网运行。
  - 算电协同需要同时处理电力可靠性、绿电比例、负荷迁移和成本优化。
  - 省级现货价格分化和市场波动可能提高数据中心跨区域负荷调度和电力成本优化价值。
counter_evidence:
  - 数据中心实际可调负荷比例可能有限。
  - 算力调度和电力调度可能由不同主体控制，价值不一定沉淀在 EMS 或 VPP 平台。
evidence_gap:
  - 需要验证数据中心实际可调负荷比例。
  - 需要验证客户是否把算电协同嵌入长期工作流。
  - 需要验证平台是否能沉淀跨客户的数据反馈优势。
confidence: medium
next_action: 跟踪数据中心需求响应案例、绿电交易和算力负荷调度数据。
```
