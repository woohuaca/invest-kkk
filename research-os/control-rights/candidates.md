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
  - 电池材料价格若持续回升，储能供给扩张速度可能低于线性降本假设，调度瓶颈会更持久。
  - 省级电力现货市场基本全覆盖，实时市场5分钟出清扩大，跨经营区交易和输电权市场化交易推进。
  - 截至2026年5月底，全国累计发电装机容量40.1亿千瓦，风光装机继续高增，但1-5月全国发电设备平均利用小时同比下降。
  - 新型能源体系试点提出源网荷储协调互济资源配置能力较2025年提升40%以上，需求侧调节能力达到最大用电负荷5%以上。
counter_evidence:
  - 监管主体或电网运营方可能吸收大部分价值。
  - 市场改革推进可能较慢。
  - 如果电池材料价格继续下行且储能利用率快速提升，部分调度瓶颈可能被供给弹性缓解。
  - 储能、虚拟电厂和车网互动聚合资源扩大后，部分实时平衡压力可能被供给侧弹性吸收。
  - 2030年政策目标不能直接证明当前调度收益和商业化可获得性。
confidence: medium
next_action: 跟踪省级现货正式运行、辅助服务市场推进、跨经营区交易常态化和需求响应实际调用。
```

## Candidate: VPP

```yaml
candidate:
  layer: VPP
  asset_type: 分布式灵活资源聚合与收益优化能力
  control_point: 虚拟电厂可能控制储能、需求响应和分布式负荷在不同市场价格信号下的聚合调度。
score:
  complexity_control: 4
  bottleneck_power: 3
  pricing_power: 3
  data_advantage: 4
  organizational_dependency: 4
  supply_response_lag: 3
  durability: 3
evidence:
  - 储能市场化推进支持分布式资源从配套资产走向可调节资源。
  - 现货市场波动和区域价格分化提高聚合调度价值。
  - 电池材料价格波动会提高储能资产收益优化和成本管理的重要性。
  - 全国新型储能装机规模达到1.36亿千瓦/3.51亿千瓦时，虚拟电厂理论调节能力超过1600万千瓦，车网互动聚合资源超过1900万千瓦。
  - 截至2026年5月底，全国充电设施数量2249.7万台、公共充电设施总功率24200万千瓦、5月充放电电量75.37亿千瓦时，充电负荷和车网互动基础扩大。
  - 新型能源体系试点提出到2030年新型储能装机3亿千瓦以上、虚拟电厂容量5000万千瓦以上、车网互动响应能力5000万千瓦以上。
counter_evidence:
  - 如果储能成本持续下降且单体资产足够便宜，VPP 的聚合溢价可能被压低。
  - 如果市场规则或电网调度入口限制第三方聚合，价值可能难以商业化沉淀。
  - 理论调节能力不等于实际调用能力、履约能力或稳定收益。
  - 充电设施规模和充放电电量不等于可调用 V2G 容量。
evidence_gap:
  - 需要验证储能利用小时、需求响应履约和聚合收益是否持续改善。
  - 需要验证客户是否把 VPP 能力嵌入长期运营流程。
confidence: medium
next_action: 跟踪 storage_cost_pressure、storage_utilization、charging_load_growth、market_volatility 和 demand_response。
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
  - VPP、车网互动和储能规模扩大提高客户侧多资产协同管理复杂度。
  - 充电设施高增提高企业园区、车队和充电运营商的负荷管理复杂性。
  - 绿证交易与非化石能源电力消费责任权重衔接，可能把绿电采购、合规核算和用电数据纳入企业能源管理流程。
counter_evidence:
  - 如果切换成本保持较低，EMS 可能商品化。
  - 公用事业公司或电网运营方可能控制调度入口。
  - 资源聚合规模扩大不等于客户组织依赖形成。
  - 绿证核算可能停留在低频合规动作，不一定沉淀为高频操作系统。
confidence: medium
next_action: 寻找企业绿电核算工作流、数据中心客户依赖、需求响应履约和数据反馈证据。
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
  - 绿证交易与非化石能源电力消费责任权重衔接后，数据中心可能需要同时管理绿电消费、证书核算、负荷调节和成本优化。
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

## Candidate: energy-export-system

```yaml
candidate:
  layer: export_system
  asset_type: 海外能源系统交付、运维与绿色属性核算能力
  control_point: 能源出口如果从设备销售上移到海外项目、EMS/VPP、长期运维和绿色属性核算，可能控制海外客户的能源系统工作流。
score:
  complexity_control: 4
  bottleneck_power: 3
  pricing_power: 3
  data_advantage: 4
  organizational_dependency: 4
  supply_response_lag: 3
  durability: 3
evidence:
  - 能源设备与服务已被识别为技术变化期可能获得阶段性瓶颈收益的环节。
  - 绿证交易与非化石能源电力消费责任权重衔接，提示绿色属性和能源数据可能进入企业采购与合规流程。
  - 海外客户如果需要光伏、储能、充电、EMS、运维和绿色属性核算的一体化方案，价值可能从一次性设备销售上移到系统和组织层。
  - IEA 2026 报告显示清洁能源技术全球市场价值在2025年接近1.2万亿美元，关键清洁能源技术贸易在2025年二季度达到历史高位，中国仍是最大出口国。
  - IEA 电网报告显示全球电网投资到2030年需接近翻倍至每年超过6000亿美元，至少3000GW可再生能源项目等待并网。
  - EU CBAM 自2026年进入正式期，进口商需要申报隐含碳排放并购买、交出证书，绿色属性和碳数据正在进入进口合规流程。
counter_evidence:
  - 能源设备出口可能陷入价格竞争，出口额增长不等于利润和控制权。
  - 贸易壁垒、本地化要求和海外认证可能削弱单纯出口模式。
  - 海外项目可能由当地 EPC、公用事业公司或渠道商控制客户关系。
  - 当前证据主要证明市场规模、贸易重定向和合规压力，尚未证明海外客户组织依赖。
evidence_gap:
  - 需要验证海外订单价格、毛利、库存和渠道质量。
  - 需要验证海外运维服务收入、续约、软件绑定和备件网络。
  - 需要验证绿色属性核算是否进入出口企业高频工作流。
confidence: low
next_action: 跟踪 energy_equipment_export_orders、overseas_grid_capex、trade_barrier_policy、overseas_om_network、export_customer_dependency 和 green_power_accounting。
```
