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
counter_evidence:
  - 如果切换成本保持较低，EMS 可能商品化。
  - 公用事业公司或电网运营方可能控制调度入口。
confidence: medium
next_action: 寻找客户依赖和数据反馈证据。
```
