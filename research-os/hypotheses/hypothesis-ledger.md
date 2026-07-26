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
last_updated: '2026-07-26'
previous_confidence: 75%
confidence_change_reason: 全国用电负荷在7月14日继续刷新至15.51亿千瓦，风光装机继续高增且利用小时下降，支持稳定容量和调度复杂性；但可再生能源十五五规划开始量化可靠替代目标，高峰期间仍未触发需求响应和有序用电，因此置信度维持不变。
supporting_evidence:
  - 新能源渗透率提升会增加系统平衡复杂性。
  - 电力市场改革可能让可靠性价值更显性。
  - 2026年1-4月太阳能和风电装机继续高增，但全国发电设备平均利用小时同比下降。
  - 发电侧容量电价机制开始覆盖煤电、气电、抽水蓄能和新型储能。
  - 2026 年部分电池材料价格出现回升迹象，提示上游资源端可能重新影响储能扩张速度。
  - 2026年1-4月全国可再生能源装机突破24亿千瓦，占全国电力总装机60.5%。
  - 截至2026年5月底，全国累计发电装机容量40.1亿千瓦，其中太阳能发电装机12.7亿千瓦、风电6.6亿千瓦，风光继续高增。
  - 2026年1-5月全国发电设备累计平均利用1155小时，同比降低95小时。
  - 2026年7月10日，全国用电负荷达到15.18亿千瓦，较历史极值增加1000万千瓦。
  - 2026年1-6月全社会用电量同比增长5.3%，充换电服务和互联网数据服务用电继续高增。
  - 2026年7月14日，全国用电负荷进一步达到15.51亿千瓦，跨省跨区跨网最大输送电力合计2.78亿千瓦。
  - 截至2026年6月底，全国累计发电装机容量40.4亿千瓦，太阳能发电装机12.7亿千瓦，风电装机6.8亿千瓦，1-6月全国发电设备累计平均利用1392小时、同比降低113小时。
  - 可再生能源十五五规划提出平均置信出力、晚高峰电量占比和新增可靠顶峰发电能力目标，说明稳定容量问题已进入可靠替代口径。
counter_evidence:
  - 储能成本可能快速下降。
  - 需求响应可能降低稳定容量稀缺性。
  - 储能市场化推进可能提高调节资源利用率，削弱稳定容量稀缺。
  - 锂、钴、镍、天然石墨价格已从高峰回落，可能继续支持储能降本和供给扩张。
  - 截至2025年底全国新型储能装机规模达到1.36亿千瓦/3.51亿千瓦时，虚拟电厂和车网互动聚合资源也在扩大。
  - 新型能源体系试点申报文件提出到2030年新型储能装机3亿千瓦以上、虚拟电厂容量5000万千瓦以上、车网互动响应能力5000万千瓦以上。
  - 充电设施数量、公共充电功率、私人接入容量和充放电电量继续高增，可能提高需求侧灵活性供给。
  - 2026年7月中旬负荷连续创新高期间，公开信息仍显示各地均未出现需求响应和有序用电，说明当前证据还不能证明稳定容量短缺已经显性化。
  - 可再生能源十五五规划同时提出新增可再生能源可靠顶峰发电能力3亿千瓦以上，若落地顺利，稳定容量稀缺可能被部分缓解。
linked_insights:
  - insights/examples/stable-capacity-becomes-scarce.md
linked_metrics:
  - renewable_penetration
  - capacity_utilization
  - peak_load_pressure
  - renewable_reliable_substitution
  - peak_valley_spread
  - dispatch_market_reform
  - storage_utilization
  - charging_load_growth
  - battery_material_price_index
  - storage_cost_pressure
  - resource_cycle_rebound
next_action: 跟踪迎峰度夏负荷、容量补偿机制、储能/VPP实际调用收益、车网互动响应能力、需求响应触发和峰时价差。
```

## Hypothesis: energy-002

```yaml
hypothesis:
  id: energy-002
  title: Dispatch Layer Gains Complexity Control
  statement: 调度层可能比单一发电资产获得更长期的复杂性控制权。
  scope: Control Point
status: active
confidence: 72%
last_updated: '2026-07-26'
previous_confidence: 72%
confidence_change_reason: 7月14日全国用电负荷再创新高且跨省跨区跨网输送电力提高，可再生能源十五五规划也把可靠替代、晚高峰支撑和系统调节能力前置，继续支持调度层复杂性控制；但新增证据主要是系统运行和政策目标，不是商业化收益兑现，因此置信度维持72%。
supporting_evidence:
  - 分布式发电和灵活负荷会提高系统复杂性。
  - 发电侧容量电价机制推动可靠容量和顶峰能力显性定价。
  - 算力设施被鼓励作为负荷侧灵活可调节资源参与电网运行。
  - 省级电力现货市场实现基本全覆盖，多个省份推动实时市场5分钟出清。
  - 云霄直流启动输电权市场化交易，跨区通道和网间互济开始更明确地进入市场化机制。
  - 新型能源体系试点提出源网荷储协调互济资源配置能力较2025年提升40%以上，需求侧调节能力达到最大用电负荷5%以上。
  - 2026年1-5月全国电力市场交易电量同比增长24.8%，现货交易电量达到3779亿千瓦时。
  - 12398通报披露风电企业未严格执行省级调度指令并被监管整改，说明调度指令具备监管可执行性。
  - 2026年7月14日高峰负荷下，跨省跨区跨网最大输送电力合计2.78亿千瓦，说明跨区互济和统一调度在高峰保障中继续增强。
  - 可再生能源十五五规划把平均置信出力、晚高峰电量占比和新增可靠顶峰能力纳入目标，调度层需要同时协调风光、灵活电源、储能、需求响应和跨区通道。
counter_evidence:
  - 电网运营方或监管主体可能限制调度价值的商业化获取。
  - 市场正式运行比例、交易深度、辅助服务收益和价格波动仍需持续验证。
  - 2030年政策目标不等于当前实际调度收益和商业化可获得性。
  - 现货交易规模仍显著小于中长期交易，灵活性价值是否充分显性化仍需验证。
  - 风电企业擅自改为人工控制的案例也说明调度指令到现场控制之间存在执行风险。
  - 跨区互济和可靠替代目标更多证明系统重要性，尚不能证明第三方平台或企业级软件能够捕获调度层收益。
linked_insights: []
linked_metrics:
  - dispatch_market_reform
  - dispatch_instruction_compliance
  - peak_load_pressure
  - renewable_reliable_substitution
  - peak_valley_spread
  - day_ahead_realtime_spread
  - congestion
  - demand_response
next_action: 跟踪 2026 年一半以上省份电力现货市场正式运行、辅助服务市场推进、跨经营区交易常态化、调度指令执行和需求响应实际调用。
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
last_updated: '2026-07-26'
previous_confidence: 65%
confidence_change_reason: 绿证核发交易规模扩大，并出现中国绿证价格指数，支持绿色属性、采购、核算和能源数据进入企业管理流程；但绿证仍可能停留在低频合规或采购动作，且缺少客户闭环控制授权、实际调用收益和切换成本案例，因此置信度维持不变。
supporting_evidence:
  - 分布式资产增长后，客户更难用人工方式管理能源系统。
  - 互联网数据服务用电快速增长，提高高可靠负荷管理需求。
  - 算电协同行动方案鼓励算力设施参与电网运行。
  - 虚拟电厂理论调节能力超过1600万千瓦，车网互动聚合资源超过1900万千瓦。
  - 全国充电设施数量、公共充电功率、私人接入容量和充放电电量继续高增，提高配网、车网互动和客户侧能源管理复杂性。
  - 绿证交易与非化石能源电力消费责任权重衔接，可能把绿电采购、合规核算和用电数据纳入企业常态工作流。
  - OT 指南更新提示 AI/ML、数字孪生、边缘计算、云平台和 5G 等技术进入 OT 环境时需要安全和控制边界，支持工业控制接入成为 EMS/VPP 前置变量。
  - 公网 OT 暴露面研究显示 ModbusTCP、EtherNet/IP、S7、HMI 和 SCADA 暴露会带来可观攻击面，说明工业控制接入需要安全分区、身份认证和审计能力。
  - 2026年1-6月充换电服务业用电量同比增长56.9%，互联网数据服务用电量同比增长44.0%，客户侧能源管理复杂性继续提高。
  - 能源数据分级指南把实时控制指令和大规模电力消费原始数据纳入重要数据或核心数据，提示能源数据闭环具备控制权价值。
  - 风电企业擅自将风机改为人工控制并违反调度指令，说明工业控制权限会直接影响调度执行和平台控制权边界。
  - 2026年6月全国核发绿证3.73亿个、交易绿证8273万个，绿色属性正在从政策核算进入可追踪交易口径。
  - 中国绿证价格指数在2026年6月收于181.0点，同比上涨23.2%，说明绿证具备连续价格观察口径，可能影响企业采购、预算、审计和能源管理。
counter_evidence:
  - 如果客户切换成本保持较低，EMS 可能商品化。
  - 理论调节能力不等于实际调用能力、客户依赖或收益稳定性。
  - 绿证核算可能停留在合规报送层面，不一定形成高频 EMS 使用或平台控制权。
  - 如果客户只开放只读采集或人工执行，不授予闭环控制权限，工业控制接入不会自动形成 EMS/VPP 控制权。
  - 如果 OT 接入增加公网暴露或停线风险，客户可能降低自动控制授权，反而削弱 EMS/VPP 的组织依赖。
  - 数据安全分级可能提高数据跨主体流动、模型训练和平台复用的合规成本。
  - 高负荷期间未出现需求响应和有序用电，仍缺少 VPP 实际调用收益证据。
  - 绿证价格指数和交易量不能证明企业把绿电采购、碳核算、审计和用电优化放进同一个高频操作系统。
  - 绿证指数2026年6月环比下跌0.2%，说明短期价格信号仍需与交易深度、履约责任和企业工作流一起判断。
linked_insights: []
linked_metrics:
  - data_center_load_growth
  - demand_response
  - charging_load_growth
  - storage_utilization
  - green_power_accounting
  - green_certificate_price_signal
  - market_volatility
  - industrial_control_integration
  - dispatch_instruction_compliance
  - customer_switching_cost
  - data_feedback_loop
next_action: 寻找企业绿电核算工作流、数据中心客户依赖、需求响应履约、VPP实际调用收益、OT接入深度、闭环控制权限、安全分区和数据反馈证据。
```

## Hypothesis: energy-004

```yaml
hypothesis:
  id: energy-004
  title: Energy Export Moves From Products To Systems
  statement: 能源出口的长期控制权不在一次性设备出口，而在海外能源系统、长期运维、EMS/VPP和绿色属性核算。
  scope: Control Point / Industry
status: active
confidence: 55%
last_updated: '2026-07-26'
previous_confidence: 55%
confidence_change_reason: 2026年上半年机电产品、锂电池、风力发电机组和汽车出口继续高增，增强能源出口大市场和制造外溢证据；但新增事实仍主要证明设备出口能力，尚未证明海外客户续约、软件绑定、运维收入或高切换成本，因此置信度维持55%。
supporting_evidence:
  - 清洁能源技术全球市场价值在2025年接近1.2万亿美元，关键清洁能源技术贸易在2025年二季度达到历史高位。
  - 在既定政策情景下，清洁能源技术全球净贸易额预计从2025年的2900亿美元增至2035年的6200亿美元，中国仍是最大出口国。
  - 中国电动车出口在2025年约500亿美元，新兴经济体占中国电动车出口比例已接近40%。
  - 全球电网投资到2030年需接近翻倍至每年超过6000亿美元，至少3000GW可再生能源项目等待并网。
  - 欧盟CBAM自2026年进入正式期，进口商需要申报隐含碳排放并购买、交出CBAM证书。
  - 2026年上半年中国机电产品出口9.36万亿元，同比增长20.1%；锂电池、风力发电机组和汽车出口分别同比增长37.6%、35.6%和65.3%。
counter_evidence:
  - 能源设备出口可能陷入价格竞争和毛利压缩。
  - 关税、反补贴、本地化要求和认证规则可能削弱纯出口模式。
  - 海外项目的客户关系可能由当地公用事业公司、EPC或渠道商控制。
  - 当前证据还不能证明海外客户续约、软件绑定、运维收入或高切换成本。
  - 出口交货值和品类增速可能来自设备需求、补库存或价格竞争，不能直接推出系统控制权。
linked_insights:
  - insights/examples/energy-export-shifts-to-systems.md
linked_metrics:
  - energy_equipment_export_orders
  - overseas_grid_capex
  - trade_barrier_policy
  - overseas_om_network
  - export_customer_dependency
  - green_power_accounting
next_action: 跟踪海外订单价格、毛利、库存、海外运维服务收入、EMS/VPP软件绑定、绿电/碳足迹核算案例和客户续约证据。
```
