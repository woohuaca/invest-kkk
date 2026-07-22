# 能源出口观察标的池

## 结论

当前适合建立能源出口观察标的池，但只用于验证 `energy-004`，不用于股票推荐、交易动作或仓位判断。

第一批观察对象应优先放在控制点和资产类型上，而不是先列公司。原因是能源出口的核心问题不是“谁出口额最大”，而是谁能把海外客户从一次性设备采购带入系统交付、长期运维、EMS/VPP、绿色属性核算和数据闭环。

## 观察边界

- 本文件只记录观察对象、验证问题和反证条件。
- `priority` 表示研究优先级，不表示投资吸引力。
- 具体公司进入观察池前，必须补充海外收入、订单质量、毛利、服务收入、软件绑定或客户依赖证据。
- 出口额增长不能单独证明控制权。

## 来源刷新

```yaml
source_refresh:
  date: '2026-07-22'
  sources:
    - name: IEA Energy Technology Perspectives 2026
      url: https://www.iea.org/reports/energy-technology-perspectives-2026/executive-summary
      read_through: 清洁能源技术贸易仍是大市场，但关税、本地化和贸易重定向改变出口玩法。
    - name: IEA Electricity Grids and Secure Energy Transitions
      url: https://www.iea.org/reports/electricity-grids-and-secure-energy-transitions/executive-summary
      read_through: 海外电网投资缺口强化电网设备、并网、调度和长期运维观察价值。
    - name: European Commission Carbon Border Adjustment Mechanism
      url: https://taxation-customs.ec.europa.eu/carbon-border-adjustment-mechanism_en
      read_through: CBAM 正式期把隐含碳排放、证书和审计数据纳入进口流程。
    - name: SCIO 2026 H1 China foreign trade briefing
      url: https://english.scio.gov.cn/pressroom/2026-07/14/content_118603461.html
      read_through: 中国上半年出口保持增长，机电产品仍是出口主线。
    - name: SCIO equipment manufacturing export update
      url: https://english.scio.gov.cn/pressroom/2026-07/20/content_118608649.html
      read_through: 锂电池、风力发电机组和汽车等设备出口继续体现中国能源制造外溢能力。
```

## 优先级口径

| 优先级 | 含义 | 进入条件 |
| --- | --- | --- |
| A | 立即研究候选 | 同时具备市场增量、瓶颈或合规压力，并可能进入客户长期流程 |
| B | 观察/等待触发 | 市场方向明确，但还缺少服务收入、软件绑定或客户依赖证据 |
| C | 屏幕标记 | 概念相关，但暴露度、控制权或商业化路径尚未证明 |

## 观察对象看板

| 优先级 | 观察对象 | 控制点 | 关键验证 | 第一反证 |
| --- | --- | --- | --- | --- |
| A | 海外电网设备与变压器 | 并网瓶颈、交付周期、认证和服务网络 | 海外电网投资、变压器订单、并网项目、备件和服务收入 | 当地公用事业公司控制客户关系，设备商只做低毛利供货 |
| A | 储能系统集成与 PCS/BMS/EMS | 多资产协同、调度入口、系统软件 | 海外储能项目是否绑定 EMS、运维和收益优化 | 电芯或硬件价格战吞噬利润，系统集成缺少差异 |
| A | 绿色属性与 CBAM 核算 | 碳数据、绿电证明、审计和采购流程 | 出口企业是否把绿电、碳足迹、证书和能源数据接入持续工作流 | 只是一年一次低频报送，不能形成高切换成本 |
| A | 光伏逆变器与能源管理平台 | 设备入口、监控数据、软件平台 | 海外客户是否使用平台做监控、运维、储能和负荷管理 | 逆变器硬件商品化，软件不收费或不可留存 |
| B | 工商业微电网和离网能源系统 | 项目开发、运维、客户现场控制 | 是否从 EPC 进入 O&M、能源管理和扩容关系 | 项目一次性收入，客户后续由本地运营商接管 |
| B | 海外充电基础设施与车网互动 | 充电运营、负荷管理、V2G 接口 | 是否绑定站点运营、支付、EMS 和需求响应 | 中国车出口不带来充电网络控制权 |
| B | 风电设备与海外服务 | 大型设备交付、备件、运维合同 | 海外风机订单是否带来长期服务、备件和本地运维 | 项目周期强，服务利润不足，认证和政治风险高 |
| B | 海外本地化产能与渠道 | 关税规避、准入、渠道和售后 | 本地化是否提高准入和客户留存，而不是只增加资本开支 | 本地化推高成本，弱化中国供应链优势 |
| B | 海外长期运维网络 | 备件、响应速度、客户续约 | 是否形成服务收入、续约和跨项目数据积累 | 运维被当地 EPC、渠道商或业主内部团队吸收 |
| C | 数据中心电力系统与储能备电出海 | 高可靠供电、储能备电、能源优化 | 是否能证明海外 AI/数据中心客户采用中国电力系统方案 | 暴露度不清，可能只是普通电气设备销售 |

## 观察卡片

```yaml
target:
  id: ee-001
  name: 海外电网设备与变压器
  type: control_point
  priority: A
  control_point: 海外电网投资缺口、并网瓶颈、设备交付周期、认证和服务网络。
  why_watch: 全球电网投资需要提升，新能源并网等待强化电网设备和配网系统需求。
  evidence_needed:
    - 海外电网、配网、变压器和并网项目订单。
    - 交付周期、价格、毛利和产能利用率。
    - 备件、调试、运维和本地服务收入。
  counter_evidence:
    - 当地公用事业公司或 EPC 控制客户关系。
    - 设备商只做低毛利供货。
  linked_metrics:
    - overseas_grid_capex
    - overseas_om_network
    - trade_barrier_policy
  status: active
  next_action: 回溯海外电网投资、变压器供需和中国设备企业海外订单披露。
```

```yaml
target:
  id: ee-002
  name: 储能系统集成与 PCS/BMS/EMS
  type: control_point
  priority: A
  control_point: 储能系统的软件、功率变换、资产协同和调度优化入口。
  why_watch: 电池出口只能说明供给能力，系统集成和 EMS 才可能控制海外客户运行逻辑。
  evidence_needed:
    - 海外储能项目是否绑定 PCS、BMS、EMS 和长期运维。
    - 项目收入中硬件、软件、服务和运维占比。
    - 客户续约、扩容和收益优化案例。
  counter_evidence:
    - 电芯和硬件价格战压低系统利润。
    - 项目交付后客户转向本地运营商或自运维。
  linked_metrics:
    - energy_equipment_export_orders
    - overseas_om_network
    - export_customer_dependency
  status: active
  next_action: 查找海外储能项目披露中的软件、运维和收益优化证据。
```

```yaml
target:
  id: ee-003
  name: 绿色属性与 CBAM 核算
  type: control_point
  priority: A
  control_point: 出口商品隐含碳、绿电采购、证书、PPA、审计和能源数据工作流。
  why_watch: CBAM 正式期提高出口企业对碳数据和能源属性证明的持续需求。
  evidence_needed:
    - 出口企业是否建立绿电、绿证、碳足迹和能源数据一体化流程。
    - 核算系统是否接入采购、生产、审计和客户交付流程。
    - 是否形成持续服务费、审计接口或客户切换成本。
  counter_evidence:
    - 合规停留在低频报送。
    - 审计和咨询机构掌握客户关系，软件平台只做工具。
  linked_metrics:
    - green_power_accounting
    - trade_barrier_policy
    - export_customer_dependency
  status: active
  next_action: 跟踪 CBAM、绿电采购、碳足迹和出口产品合规案例。
```

```yaml
target:
  id: ee-004
  name: 光伏逆变器与能源管理平台
  type: control_point
  priority: A
  control_point: 逆变器设备入口、监控数据、储能协同和客户能源管理平台。
  why_watch: 光伏硬件容易价格竞争，但逆变器和能源管理平台更接近数据入口和运维关系。
  evidence_needed:
    - 海外逆变器出货是否绑定监控平台和售后服务。
    - 储能、充电和负荷管理是否在同一平台内扩展。
    - 软件收费、客户留存和跨项目数据能力。
  counter_evidence:
    - 逆变器成为低毛利硬件。
    - 平台只是免费售后工具，无法形成定价权。
  linked_metrics:
    - energy_equipment_export_orders
    - data_feedback_loop
    - export_customer_dependency
  status: active
  next_action: 查找海外平台活跃设备数、服务收入和客户留存披露。
```

```yaml
target:
  id: ee-005
  name: 工商业微电网和离网能源系统
  type: asset_type
  priority: B
  control_point: 光伏、储能、柴油/燃气备份、EMS 和现场运维的一体化系统。
  why_watch: 新兴市场、园区、矿山、岛屿和高可靠负荷可能需要系统方案而非单品采购。
  evidence_needed:
    - 项目是否从 EPC 延伸到长期 O&M 和能源管理。
    - 客户是否持续采购扩容、运维和系统优化。
    - 是否接入生产负荷、充电、储能和绿电核算。
  counter_evidence:
    - 项目一次性建设收入占主导。
    - 后续运营由当地能源公司或客户内部团队接管。
  linked_metrics:
    - overseas_grid_capex
    - overseas_om_network
    - export_customer_dependency
  status: watch
  next_action: 寻找海外工商业微电网项目中的 O&M、EMS 和续约证据。
```

```yaml
target:
  id: ee-006
  name: 海外充电基础设施与车网互动
  type: asset_type
  priority: B
  control_point: 充电运营、站点能源管理、支付结算、负荷响应和 V2G 接口。
  why_watch: 电动车出口会带来补能基础设施需求，但控制权取决于谁掌握站点运营和能源管理。
  evidence_needed:
    - 海外充电网络是否与车辆、储能和 EMS 联动。
    - 充电运营商、车企和电力公司之间的客户关系归属。
    - V2G、需求响应或站点储能收益案例。
  counter_evidence:
    - 车出口增长不带来充电网络控制权。
    - 当地运营商和电力公司掌握站点和客户数据。
  linked_metrics:
    - charging_load_growth
    - demand_response
    - export_customer_dependency
  status: watch
  next_action: 跟踪海外充电项目是否披露站点运营、EMS 和 V2G 接口。
```

```yaml
target:
  id: ee-007
  name: 风电设备与海外服务
  type: asset_type
  priority: B
  control_point: 大型设备认证、备件、长期运维和本地服务网络。
  why_watch: 风机出口如果绑定长期服务，可能从设备销售转为运维关系。
  evidence_needed:
    - 海外风机订单、并网项目、服务合同和备件收入。
    - 本地团队、认证、可用率保证和运维年限。
    - 价格和毛利在海外扩张中的变化。
  counter_evidence:
    - 项目周期强，交付后服务利润不足。
    - 政治、认证和本地化风险提高履约成本。
  linked_metrics:
    - energy_equipment_export_orders
    - overseas_om_network
    - trade_barrier_policy
  status: watch
  next_action: 查找风电设备出海是否从订单转化为长期服务利润。
```

```yaml
target:
  id: ee-008
  name: 海外本地化产能与渠道
  type: constraint
  priority: B
  control_point: 关税规避、本地认证、渠道、售后和客户接入。
  why_watch: 贸易壁垒会改变能源出口玩法，本地化可能从成本项变成准入和客户关系入口。
  evidence_needed:
    - 本地工厂、渠道、认证和售后网络是否提高准入。
    - 本地化后订单质量、交付速度和客户留存是否改善。
    - 本地化资本开支和毛利率变化。
  counter_evidence:
    - 本地化只增加资本开支和运营复杂性。
    - 供应链优势被削弱，客户仍以价格选择供应商。
  linked_metrics:
    - trade_barrier_policy
    - overseas_om_network
    - export_customer_dependency
  status: watch
  next_action: 跟踪关税、本地化要求和海外产能利用率。
```

```yaml
target:
  id: ee-009
  name: 海外长期运维网络
  type: control_point
  priority: B
  control_point: 备件、响应速度、调试能力、服务收入、客户续约和运行数据。
  why_watch: 运维网络是设备出口变成客户关系的关键桥。
  evidence_needed:
    - 海外服务网点、备件仓、运维团队和响应 SLA。
    - 服务收入、续约率、毛利率和客户扩容。
    - 运维数据是否反哺产品和软件。
  counter_evidence:
    - 运维由当地 EPC、渠道商或客户内部团队吸收。
    - 服务收入规模小，无法改变商业模式。
  linked_metrics:
    - overseas_om_network
    - data_feedback_loop
    - customer_retention
  status: watch
  next_action: 建立海外运维证据模板，后续用于公司级观察。
```

```yaml
target:
  id: ee-010
  name: 数据中心电力系统与储能备电出海
  type: screen_flag
  priority: C
  control_point: 高可靠供电、UPS/储能备电、能源优化和绿电核算。
  why_watch: AI 和数据中心扩张会抬高海外电力系统需求，但当前与中国能源出口控制权的连接仍需证明。
  evidence_needed:
    - 海外数据中心客户是否采购中国电力系统、储能、EMS 或绿电核算方案。
    - 是否存在长期运维、扩容和高可靠服务合同。
    - 是否进入客户能源管理或合规工作流。
  counter_evidence:
    - 只是普通电气设备销售。
    - 客户选择全球电气巨头或本地系统集成商。
  linked_metrics:
    - data_center_load_growth
    - overseas_grid_capex
    - export_customer_dependency
  status: screen_flag_only
  next_action: 先验证主题暴露，不进入公司级观察池。
```

## 下一步

- 第一轮公司级观察只选择 6-8 个对象，且必须有明确 `exposure proof`。
- 每个公司观察对象必须说明它验证哪个控制点，而不是只说明它属于新能源出口。
- 对没有软件绑定、服务收入、客户续约或合规工作流证据的对象，保持 `needs exposure attribution`。
