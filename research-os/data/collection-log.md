# 数据采集日志

## 结论

本文件记录每周能源行业信号。所有记录必须符合 `schemas/weekly-signal.md`。

## 2026-06-05

```yaml
signal:
  title: 稳定容量可能变得更稀缺
  source: Energy Research OS v0.1 种子记录
  source_url: https://github.com/woohuaca/invest-kkk/blob/main/research-os/data/collection-log.md
  date: '2026-06-05'
  topic: power_market
  layer: dispatch
  fact: 新能源渗透率提高会增加对可靠容量和调节能力的需求。
strength: medium
confidence: medium
impact: 支持稳定容量和调度能力可能成为控制点的假设。
next_action: 链接到 insights/examples/stable-capacity-becomes-scarce.md 和 hypotheses/hypothesis-ledger.md。
```

## 2026-06-09

```yaml
signal:
  title: 风光装机高增叠加利用小时下降
  source: 国家能源局 2026年1-4月份全国电力统计数据
  source_url: https://www.nea.gov.cn/20260525/c509435a0f09497cb3d2ca361fa262de/c.html
  date: '2026-05-25'
  topic: power_market
  layer: dispatch
  fact: 截至2026年4月底，全国发电装机容量39.9亿千瓦，其中太阳能发电12.5亿千瓦、同比增长26.2%，风电6.6亿千瓦、同比增长22.0%；1-4月全国发电设备平均利用925小时、同比减少84小时。
strength: strong
confidence: high
impact: renewable_penetration 上升并伴随利用小时下降，支持调度复杂性和稳定容量稀缺假设。
next_action: 更新 metrics/calculation-log.md 的 renewable_penetration 与 capacity_utilization，并更新 hypotheses/hypothesis-ledger.md 的 energy-001。
```

```yaml
signal:
  title: 发电侧容量电价机制强化顶峰能力价值
  source: 国家发展改革委、国家能源局 关于完善发电侧容量电价机制的通知
  source_url: https://www.ndrc.gov.cn/xxgk/jd/jd/202601/t20260130_1403521.html
  date: '2026-01-30'
  topic: power_market
  layer: dispatch
  fact: 政策要求分类完善煤电、气电、抽水蓄能和新型储能容量电价机制，并在电力现货市场连续运行后有序建立发电侧可靠容量补偿机制。
strength: strong
confidence: high
impact: dispatch_market_reform 支持可靠容量、顶峰能力和调节价值显性定价。
next_action: 更新 metrics/calculation-log.md 的 dispatch_market_reform，并提高 control-rights/candidates.md 中 dispatch-layer 的证据强度。
```

```yaml
signal:
  title: 互联网数据服务用电保持高增
  source: 国家能源局 2026年4月份全社会用电量数据
  source_url: https://cpnn.com.cn/news/xwtt/202605/t20260519_1888692.html
  date: '2026-05-19'
  topic: data_center
  layer: distribution
  fact: 2026年4月互联网数据服务用电量82亿千瓦时，同比增长42.8%；1-4月累计312亿千瓦时，同比增长44.4%。
strength: strong
confidence: high
impact: data_center_load_growth 抬高配电侧高可靠负荷管理和算电协同的重要性。
next_action: 更新 metrics/calculation-log.md 的 data_center_load_growth，并观察是否形成新的控制点候选。
```

```yaml
signal:
  title: 算力设施被纳入负荷侧灵活调节资源
  source: 国家发展改革委、国家能源局、工业和信息化部、国家数据局 关于促进人工智能与能源双向赋能的行动方案
  source_url: https://www.nda.gov.cn/sjj/zwgk/zcfb/0508/20260508194112925527578_pc.html
  date: '2026-05-08'
  topic: data_center
  layer: EMS
  fact: 行动方案提出保障算力设施安全可靠能源供给、促进算力电力高效经济协同，并鼓励算力设施作为负荷侧灵活可调节资源参与电网运行。
strength: strong
confidence: high
impact: demand_response、data_feedback_loop 和 organizational_dependency 可能在算电协同场景中增强。
next_action: 在 control-rights/candidates.md 新增或更新算电协同候选控制点。
```

```yaml
signal:
  title: 甘肃推动电网侧储能参与中长期市场
  source: 国家能源局甘肃监管办公室 电网侧储能参与中长期市场进展
  source_url: https://gsb.nea.gov.cn/dtyw/jgdt/202605/t20260515_301162.html
  date: '2026-05-15'
  topic: storage
  layer: VPP
  fact: 甘肃推动电网侧储能参与中长期市场，新型储能并网规模达到966万千瓦。
strength: medium
confidence: high
impact: storage_utilization 正在从并网配套走向市场调节价值，支持储能从资源层进入调度和聚合层。
next_action: 更新 metrics/calculation-log.md 的 storage_utilization，并跟踪储能调用频率。
```

```yaml
signal:
  title: 山东新能源配储利用率偏低形成反证
  source: 国家能源局山东监管办公室 新能源配储一体化参与电力市场进展
  source_url: https://sdb.nea.gov.cn/dtyw/jgdt/202604/t20260427_300325.html
  date: '2026-04-27'
  topic: storage
  layer: VPP
  fact: 山东推动新能源配建储能一体化参与电力市场，以解决配储利用率偏低、作用发挥不充分问题。
strength: medium
confidence: high
impact: storage_utilization 仍是稳定容量稀缺假设的关键反证；如果利用率快速提升，稳定容量稀缺可能被部分缓解。
next_action: 在 hypotheses/hypothesis-ledger.md 保留 energy-001 的储能反证，并持续观察储能利用小时和价差。
```

## 2026-06-10

```yaml
signal:
  title: 电力现货价格呈现区域分化和价差波动
  source: 朗新能源研究院「观价」电力现货市场数据洞察
  source_url: 'https://mp.weixin.qq.com/s/-5P4z7NF0WaoCTbBwhcg8g'
  date: '2026-06-10'
  topic: power_market
  layer: dispatch
  fact: 文章跟踪山西、广东、山东、甘肃、浙江、陕西、辽宁、安徽 8 个省级电力现货市场，指出 2026 年 5 月 16 日至 31 日重点省份价格延续显著区域分化，广东、浙江实时均价超过 400 元/兆瓦时并高于或接近燃煤基准价，多数省份环比上涨。
strength: medium
confidence: medium
impact: day_ahead_realtime_spread、regional_price_divergence 和 market_volatility 可能成为调度、预测、储能、EMS/VPP 的领先观察指标。
next_action: 将朗新能源研究院「观价」纳入二级观察源，并在 metrics/metric-catalog.md 增加现货市场价差和区域分化指标。
```

## 2026-06-12

```yaml
signal:
  title: 电池材料价格回落后出现修复迹象
  source: REAI Lab《盛宴不再》
  source_url: 'https://mp.weixin.qq.com/s/eja5Th27GErdg69dxXlh1A'
  date: '2026-06-12'
  topic: storage
  layer: VPP
  fact: 文章引用 Visual Capitalist / Benchmark Mineral Intelligence 图表，指出锂、钴、镍、天然石墨价格在 2023 年前后冲高后回落，2026 年部分材料价格出现回升迹象。
strength: medium
confidence: medium
impact: battery_material_price_index、storage_cost_pressure 和 resource_cycle_rebound 会影响储能扩张速度，进而改变稳定容量稀缺、调度瓶颈和 VPP 控制权判断。
next_action: 回溯 Benchmark Mineral Intelligence、Visual Capitalist 或其他大宗商品数据源，验证锂、钴、镍、天然石墨价格是否持续回升。
```

## 2026-06-22

```yaml
signal:
  title: 可再生能源装机突破24亿千瓦并要求提升五大消纳能力
  source: 国家能源局 全国可再生能源电力开发建设月度（6月）调度视频会
  source_url: https://www.nea.gov.cn/20260616/ab30f2b505764d13972ac14e7d3ffeed/c.html
  date: '2026-06-16'
  topic: power_market
  layer: dispatch
  fact: 2026年1-4月，全国可再生能源发电装机突破24亿千瓦，占全国电力总装机60.5%；新增装机7516万千瓦，占全部新增装机70.7%；会议要求提升电网接入、调节、调度、预测、跨区互济五大能力，并依托价格信号带动储能发展。
strength: strong
confidence: high
impact: renewable_penetration、grid_connection_delay、congestion、dispatch_market_reform 同时增强，支持高比例新能源下的调度复杂性和消纳瓶颈观察。
next_action: 更新 metrics/calculation-log.md 的 renewable_penetration 和 dispatch_market_reform，并在 energy-001 中保持储能供给弹性反证。
```

```yaml
signal:
  title: 全国统一电力市场体系初步建成且新型经营主体扩围
  source: 国家能源局页面《2025年度中国电力市场发展报告》发布
  source_url: https://www.nea.gov.cn/20260618/41e848b9ec6543998757db3864e01ab2/c.html
  date: '2026-06-18'
  topic: power_market
  layer: dispatch
  fact: 报告显示省级电力现货市场实现基本全覆盖，全国新型储能装机规模达到1.36亿千瓦/3.51亿千瓦时，虚拟电厂理论调节能力超过1600万千瓦，车网互动聚合资源超过1900万千瓦，21个省区市或地区实现新能源报量报价参与现货市场，江西、山西推动实时市场5分钟出清。
strength: strong
confidence: high
impact: dispatch_market_reform、storage_utilization、demand_response 和 VPP 候选控制点证据增强，但理论调节能力仍需和实际调用收益区分。
next_action: 更新 energy-002 和 energy-003，区分市场机制成熟、资源聚合规模和客户组织依赖三类证据。
```

```yaml
signal:
  title: 云霄直流启动输电权市场化交易
  source: 国家能源局 两部门部署在云霄直流开展输电权市场化交易
  source_url: https://www.nea.gov.cn/20260612/6d9c29711f3a4718b121b467cd0f0215/c.html
  date: '2026-06-12'
  topic: grid
  layer: transmission
  fact: 国家发展改革委、国家能源局提出自2026年6月1日起，按照云霄直流输电权市场化交易方案，以月度及以内交易起步，在云霄直流通道开展输电权市场化交易，用于挖掘输电通道潜力、提升通道利用效率、支撑网间互济互保和常态化交易需求。
strength: medium
confidence: high
impact: congestion 和 dispatch_market_reform 从省内现货扩展到跨网输电通道，提示输电权和跨区交易可能成为统一电力市场的重要控制点。
next_action: 在 metrics/calculation-log.md 增加 congestion / transmission-rights 观察，并持续跟踪跨经营区交易常态化。
```

```yaml
signal:
  title: 12398通报显示配网承载力和新能源并网仍是热点问题
  source: 国家能源局12398能源监管热线投诉举报处理情况通报（2026年5月）
  source_url: https://www.nea.gov.cn/20260622/c9c23bedf4c24757a6a087c763362095/c.html
  date: '2026-06-22'
  topic: grid
  layer: distribution
  fact: 2026年5月，12398热线平台接收投诉1832件，热点包括多次停电、低电压、用电报装、电表计量等；通报要求加强电能质量治理、推进新增配变布点和变电增容，并规范新能源并网管理，做好接入受限台区、反向过载台区等监测。
strength: medium
confidence: high
impact: grid_connection_delay、local_load_growth 和 congestion 提示配网承载力仍可能成为分布式新能源、充电桩和工商业用能的局部瓶颈。
next_action: 跟踪低电压、台区承载力、新能源接入受限案例是否持续，并判断是否强化 distribution 层控制点。
```

## 2026-06-29

```yaml
signal:
  title: 全国发电装机突破40亿千瓦但利用小时继续下降
  source: 国家能源局 2026年1-5月份全国电力工业统计数据
  source_url: https://www.nea.gov.cn/20260623/536f34aa643449749ab37af6c02a0254/c.html
  date: '2026-06-23'
  topic: power_market
  layer: dispatch
  fact: 截至2026年5月底，全国累计发电装机容量40.1亿千瓦，同比增长17.8%；太阳能发电装机12.7亿千瓦、同比增长24.4%，风电6.6亿千瓦、同比增长21.6%；1-5月全国发电设备累计平均利用1155小时、同比降低95小时。
strength: strong
confidence: high
impact: renewable_penetration 与 capacity_utilization 同时增强，支持资源侧扩张快于有效利用、调度复杂性继续上升的观察。
next_action: 更新 metrics/calculation-log.md，并在 energy-001 中同时记录高渗透支持证据和储能供给弹性反证。
```

```yaml
signal:
  title: 充电设施规模和充放电电量继续高增
  source: 国家能源局 2026年5月全国电动汽车充电设施数据
  source_url: https://www.nea.gov.cn/20260623/fd6b7ebd6f03404286ef8d13c4ce51fd/c.html
  date: '2026-06-23'
  topic: grid
  layer: distribution
  fact: 截至2026年5月底，全国充电设施数量2249.7万台、同比增长47.5%；公共充电设施总功率24200万千瓦、同比增长43.5%；私人充电设施接入容量15107.8万千伏安、同比增长48.3%；2026年5月全国充放电电量75.37亿千瓦时、同比增长46.4%。
strength: strong
confidence: high
impact: charging_load_growth、local_load_growth、grid_connection_delay 和 demand_response 同时增强，提示充电负荷、车网互动和配网承载力会影响 VPP 与 distribution 控制点。
next_action: 新增 charging_load_growth 指标，并在 VPP / EMS 候选中区分设施规模、实际充放电量和调度响应能力。
```

```yaml
signal:
  title: 新型能源体系试点明确2030年储能、VPP和车网互动目标
  source: 国家能源局 新型能源体系建设第一批试点申报文件
  source_url: https://www.nea.gov.cn/20260625/0ccfdc1674e84868b49480edf584eb5f/c.html
  date: '2026-06-25'
  topic: policy
  layer: VPP
  fact: 第一批试点申报文件提出到2030年全国发电总装机约54亿千瓦、非化石能源发电量占比50%左右，源网荷储协调互济资源配置能力较2025年提升40%以上，需求侧调节能力达到最大用电负荷5%以上，配电网具备约9亿千瓦分布式新能源接入能力，新型储能装机3亿千瓦以上，虚拟电厂容量5000万千瓦以上，车网互动响应能力5000万千瓦以上。
strength: strong
confidence: high
impact: dispatch_market_reform、demand_response、storage_utilization、charging_load_growth 和 VPP 候选控制点证据增强，但仍需要实际调用收益和客户依赖验证。
next_action: 更新 energy-002 和 energy-003，并将 VPP 目标从理论容量跟踪转向实际调用能力和收益稳定性。
```

```yaml
signal:
  title: 非公共电网常规水电纳入绿证核发数据链
  source: 国家能源局 非公共电网存量常规水电项目绿证核发通知
  source_url: https://www.nea.gov.cn/20260626/78be814353a74763a086e024c788422a/c.html
  date: '2026-06-26'
  topic: policy
  layer: operations_knowledge
  fact: 国家能源局要求相关项目在2026年7月31日前完成绿证账户创建或划转，并在2026年8月31日前提交2023年1月至2025年12月历史生产数据；符合条件的电量可自2023年1月1日起核发绿证。
strength: medium
confidence: high
impact: green_power_accounting 和 data_feedback_loop 可能把发电数据、证书核发和用户侧核算连接为新的能源数据基础设施。
next_action: 新增 green_power_accounting 指标，并观察绿证数据是否从政策报送走向企业常态化用能管理。
```

```yaml
signal:
  title: 绿证交易与非化石能源电力消费责任权重衔接
  source: 国家能源局 进一步做好非化石能源电力消费与绿证衔接工作
  source_url: https://www.nea.gov.cn/20260626/0cbab29ffce74340bf1f23b0fa8c8a50/c.html
  date: '2026-06-26'
  topic: policy
  layer: EMS
  fact: 文件明确从2026年开始，绿色电力证书交易可用于完成用户非化石能源消费责任权重，推动非化石能源电力消费和绿证核算衔接。
strength: medium
confidence: high
impact: green_power_accounting、customer_switching_cost 和 data_feedback_loop 可能把企业绿电采购、合规核算和能源管理工作流连接起来。
next_action: 观察企业侧是否出现合规、采购、用电数据一体化流程，以及该流程是否沉淀到 EMS 或 operations_knowledge 层。
```

```yaml
signal:
  title: 清洁能源技术贸易在关税扰动下仍处高位
  source: IEA Energy Technology Perspectives 2026
  source_url: https://www.iea.org/reports/energy-technology-perspectives-2026/executive-summary
  date: '2026-03-26'
  topic: energy_export
  layer: export_system
  fact: IEA指出，清洁能源技术全球市场价值在2025年接近1.2万亿美元，关键清洁能源技术国际贸易在2025年二季度达到历史高位；在既定政策情景下，相关技术全球净贸易额预计从2025年的2900亿美元增至2035年的6200亿美元，中国仍是最大出口国，2035年净出口价值预计达到3750亿美元；中国电动车出口在2025年约500亿美元，新兴经济体占中国电动车出口的比例已接近40%。
strength: strong
confidence: high
impact: energy_equipment_export_orders 与 trade_barrier_policy 同时增强，说明能源出口是大市场，但关税和市场重定向会改变出口玩法。
next_action: 更新 metrics/calculation-log.md，并在 energy-004 中区分设备贸易规模和系统控制权。
```

```yaml
signal:
  title: 全球电网投资缺口强化海外电网设备和系统机会
  source: IEA Electricity Grids and Secure Energy Transitions
  source_url: https://www.iea.org/reports/electricity-grids-and-secure-energy-transitions/executive-summary
  date: '2023-10-17'
  topic: energy_export
  layer: export_system
  fact: IEA指出，为实现各国能源和气候目标，到2040年全球需要新增或改造超过8000万公里电网；至少3000GW可再生能源项目正在等待并网；全球电网投资长期停滞在每年约3000亿美元，到2030年需接近翻倍至每年超过6000亿美元。
strength: strong
confidence: high
impact: overseas_grid_capex 增强，提示海外电网、配网、变压器、并网、EMS和长期运维可能成为能源出口的重要需求池。
next_action: 在 energy-export-system 候选中增加海外电网瓶颈证据，并寻找海外项目运维、软件和本地服务网络证据。
```

```yaml
signal:
  title: EU CBAM正式期把碳数据和证书义务嵌入进口流程
  source: European Commission Carbon Border Adjustment Mechanism
  source_url: https://taxation-customs.ec.europa.eu/carbon-border-adjustment-mechanism_en
  date: '2026-06-23'
  topic: energy_export
  layer: operations_knowledge
  fact: 欧盟CBAM自2026年1月1日进入正式期，超过50吨门槛的CBAM商品进口商需申请授权申报人资格、购买CBAM证书、申报进口商品隐含碳排放并按年交出相应证书；CBAM初始覆盖水泥、钢铁、铝、化肥、电力和氢等品类，欧盟已于2026年公布首个CBAM证书价格并更新正式期材料。
strength: strong
confidence: high
impact: trade_barrier_policy、green_power_accounting 和 export_customer_dependency 同时增强，提示出口企业需要把能源、碳、绿电和审计数据纳入合规工作流。
next_action: 观察出口企业是否把绿电采购、碳足迹、证书、审计和能源管理系统连接为持续工作流。
```

## 2026-06-30

```yaml
signal:
  title: OT 指南更新把工业控制接入变成 EMS/VPP 前置约束
  source: NIST SP 800-82 Rev.4 Initial Preliminary Draft Call for Comments
  source_url: https://csrc.nist.gov/pubs/sp/800/82/r4/iprd
  date: '2026-01-22'
  topic: policy
  layer: EMS
  fact: NIST 启动 SP 800-82 Rev.4 预草案征求意见，修订方向包括反映 OT 威胁环境变化，纳入更新后的 OT 标准和实践，并扩展 AI/ML、数字孪生、边缘计算、云平台和 5G 等技术在 OT 环境中的指导。
strength: medium
confidence: high
impact: industrial_control_integration 增强，说明 EMS/VPP 若要进入工业现场的闭环控制，需要同时处理 OT 安全、边缘响应、控制权限和新技术接入边界。
next_action: 更新 energy-003、EMS/VPP 候选和跟进看板；后续用客户案例验证只读采集、优化建议和闭环控制权限的差异。
```

```yaml
signal:
  title: 公网暴露 OT 设备显示工业控制接入有显性安全成本
  source: Analysis of Publicly Accessible Operational Technology and Associated Risks
  source_url: https://arxiv.org/abs/2508.02375
  date: '2025-08-04'
  topic: cybersecurity
  layer: operations_knowledge
  fact: 研究基于公网扫描数据识别出 68,243 个 internet-facing OT 设备，覆盖 ModbusTCP、EtherNet/IP、S7 等工业协议，并指出部分设备暴露固件、厂商和版本信息，自动化截图分析还可发现 HMI 和 SCADA 图形界面。
strength: medium
confidence: medium
impact: industrial_control_integration 增强，但更偏向反证边界：EMS/VPP 越接近闭环控制，越需要处理公网暴露、协议安全、身份认证、补丁窗口和分区隔离成本。
next_action: 后续验证 EMS/VPP 项目是否通过边缘网关、分区隔离、最小权限和审计机制接入 OT，而不是直接暴露 PLC/HMI/SCADA。
```

## 2026-07-22

```yaml
signal:
  title: 全国用电负荷创历史新高但尚未触发需求响应
  source: 国家能源局 全国用电负荷首创历史新高 国家能源局多措并举全力保障电力供应平稳有序
  source_url: https://obor.nea.gov.cn/detail2/23025.html
  date: '2026-07-15'
  topic: power_market
  layer: dispatch
  fact: 2026年7月10日，全国用电负荷达到15.18亿千瓦，较2025年7月17日历史极值15.08亿千瓦增加1000万千瓦，较7月初上涨超过1.5亿千瓦；华北、东北、西北、南方等4个区域和16个省份用电负荷累计59次创新高，各地均未出现需求响应和有序用电情况。
strength: strong
confidence: high
impact: peak_load_pressure 增强，支持稳定容量、调度和跨区互济的重要性；但未触发需求响应和有序用电，暂不证明 VPP 已经获得实际调用收益。
next_action: 新增 peak_load_pressure 指标，更新 energy-001 和 energy-002，并继续观察迎峰度夏期间是否出现需求响应、价格异常或局部停电。
```

```yaml
signal:
  title: 充换电和互联网数据服务用电继续高增
  source: 国家能源局 2026年1-6月份全社会用电量同比增长5.3%
  source_url: https://www.nea.gov.cn/20260715/ca1da417932c4fbfa26c0006f272d691/c.html
  date: '2026-07-15'
  topic: data_center
  layer: distribution
  fact: 2026年1-6月，全社会用电量累计50999亿千瓦时，同比增长5.3%；充换电服务业用电量810亿千瓦时，同比增长56.9%；互联网数据服务用电量494亿千瓦时，同比增长44.0%。2026年6月，充换电服务业和互联网数据服务用电量分别为148亿、91亿千瓦时，同比增速分别为57.1%、41.4%。
strength: strong
confidence: high
impact: charging_load_growth 和 data_center_load_growth 同时增强，提示配网承载、算电协同、EMS 和 VPP 的研究权重继续提高。
next_action: 更新 metrics/calculation-log.md、energy-003 和 EMS/VPP 候选；后续区分负荷增长、可调负荷比例和客户工作流依赖。
```

```yaml
signal:
  title: 电力市场交易电量高增但现货仍小于中长期交易
  source: 国家能源局 2026年1-5月全国电力市场交易电量同比增长24.8%
  source_url: https://www.nea.gov.cn/20260629/77ccaff0f2934369a7b94078165ceb54/c.html
  date: '2026-06-29'
  topic: power_market
  layer: dispatch
  fact: 2026年1-5月，全国累计完成电力市场交易电量30573亿千瓦时，同比增长24.8%；中长期交易电量26794亿千瓦时，现货交易电量3779亿千瓦时，绿电交易电量1364亿千瓦时，同比增长3.9%。
strength: strong
confidence: high
impact: dispatch_market_reform 增强，说明市场化交易深度继续提高；但现货交易仍显著小于中长期交易，灵活性价值是否充分显性化仍需观察。
next_action: 更新 energy-002 和 dispatch-layer 候选，后续跟踪现货交易占比、辅助服务收益和跨省跨区交易深度。
```

```yaml
signal:
  title: 风电企业不执行调度指令暴露控制权执行风险
  source: 国家能源局12398能源监管热线6月投诉举报处理情况通报
  source_url: https://www.nea.gov.cn/20260720/fa16ff39dc0d42e98753d4d9f678f674/c.html
  date: '2026-07-20'
  topic: dispatch
  layer: dispatch
  fact: 12398通报披露，江西群众举报某风力发电企业不执行电力调度指令。经核实，该企业自2026年3月以来未严格执行省级电力调度机构运行指令，擅自将风机改为人工控制，影响电网安全稳定运行；华中能源监管局已下发监管整改通知书、责令限期整改并通报批评。
strength: strong
confidence: high
impact: dispatch_instruction_compliance 和 industrial_control_integration 同时增强，说明调度层控制权不只来自市场规则，也取决于并网主体是否让控制系统按调度指令执行。
next_action: 新增 dispatch_instruction_compliance 指标，更新 energy-002、energy-003 和控制点候选；后续跟踪调度指令执行、AGC/AVC 投入和人工/自动控制边界。
```

```yaml
signal:
  title: 12398通报继续显示配网低电压和多次停电问题
  source: 国家能源局12398能源监管热线6月投诉举报处理情况通报
  source_url: https://www.nea.gov.cn/20260720/fa16ff39dc0d42e98753d4d9f678f674/c.html
  date: '2026-07-20'
  topic: grid
  layer: distribution
  fact: 2026年6月，12398热线平台接收投诉1980件，投诉热点包括部分地区电能质量不达标、台区多次停电和高峰时段低电压；典型案例显示海南海口某小区受高温天气影响用电负荷激增，供电线路在2天内发生4次故障停电。
strength: medium
confidence: high
impact: grid_connection_delay、local_load_growth 和 peak_load_pressure 增强，说明局部配网仍是高温、充电负荷和分布式新能源下的薄弱环节。
next_action: 更新 grid_connection_delay，并持续观察低电压、多次停电、充电桩报装和新能源并网投诉是否在高峰期重复出现。
```

```yaml
signal:
  title: 能源数据分级把实时控制指令和电力消费数据纳入安全边界
  source: 国家能源局有关负责同志就《能源行业数据分类分级指南（2026年版）》答记者问
  source_url: https://www.nea.gov.cn/20260630/2873fa450d2e4317b33d40285b5ed576/c.html
  date: '2026-06-30'
  topic: policy
  layer: operations_knowledge
  fact: 《能源行业数据分类分级指南（2026年版）》用于指导能源行业非密数据分类分级，识别重要数据和核心数据。国家能源局答记者问指出，重要能源设施遭到破坏或控制指令被篡改可能导致能源供应中断，部分重要能源设施精确地理坐标、实时控制指令以及能源消费类数据被列入重要数据和核心数据；1000万个及以上电力用户的电力消费原始数据为重要数据，1亿个及以上为核心数据。
strength: strong
confidence: high
impact: data_feedback_loop、industrial_control_integration 和 customer_switching_cost 同时增强，说明能源数据闭环具有潜在控制权价值，也必须被数据安全制度约束。
next_action: 更新 energy-003 和 EMS 候选；后续验证 EMS/VPP 是否能在合规边界内沉淀可复用数据反馈，而不是只增加数据合规成本。
```

```yaml
signal:
  title: 6月新增新能源项目以工商业分布式光伏为主
  source: 国家能源局 关于2026年6月全国新增建档立卡新能源发电（不含户用光伏）项目情况的公告
  source_url: https://www.nea.gov.cn/20260720/f978dbe5fcbc4d8085a3909410b9366e/c.html
  date: '2026-07-20'
  topic: grid
  layer: distribution
  fact: 2026年6月，全国新增建档立卡新能源发电项目3825个，其中风电项目32个，集中式光伏发电项目36个，工商业分布式光伏发电项目3751个，生物质发电项目6个；广东新增工商业分布式光伏项目1462个，江苏511个，浙江313个。
strength: medium
confidence: high
impact: renewable_penetration、local_load_growth 和 green_power_accounting 增强，说明新增项目继续向工商业分布式侧集中，配网接入、绿证核发和企业能源管理复杂性上升。
next_action: 更新 renewable_penetration，并观察工商业分布式光伏是否带来配网承载、反向潮流、绿证核算和 EMS 工作流依赖。
```

## 2026-07-26

```yaml
signal:
  title: 全国用电负荷再创新高且跨区互济规模扩大
  source: 全国煤炭交易中心转发国家能源局消息
  source_url: https://www.ncexc.cn/c/2026-07-16/502663.shtml
  date: '2026-07-15'
  topic: power_market
  layer: dispatch
  fact: 2026年7月14日，全国用电负荷达到15.51亿千瓦，较7月10日15.18亿千瓦继续上行；7月14日跨省跨区跨网最大输送电力合计2.78亿千瓦，较7月10日2.63亿千瓦提高，各地未出现需求响应和有序用电情况。
strength: strong
confidence: medium
impact: peak_load_pressure 和 dispatch_market_reform 增强，说明高峰负荷压力正在通过跨区互济和统一市场体系消化；但未触发需求响应，VPP实际收益仍不能上调。
next_action: 更新 peak_load_pressure 和 dispatch-layer 证据，后续跟踪跨区输电、现货价差、辅助服务和需求响应触发。
```

```yaml
signal:
  title: 上半年发电装机突破40亿千瓦但利用小时继续下降
  source: 国家能源局 2026年1-6月份全国电力统计数据
  source_url: https://www.nea.gov.cn/20260722/3b678308556b4df0a574537b59a28731/c.html
  date: '2026-07-22'
  topic: power_market
  layer: generation
  fact: 截至2026年6月底，全国累计发电装机容量40.4亿千瓦，同比增长10.8%；太阳能发电装机容量12.7亿千瓦，同比增长15.8%；风电装机容量6.8亿千瓦，同比增长18.5%；1-6月份全国发电设备累计平均利用1392小时，比上年同期降低113小时。
strength: strong
confidence: high
impact: renewable_penetration 和 capacity_utilization 同时增强，说明资源侧继续扩张，但有效利用与系统调度仍是关键约束。
next_action: 更新 energy-001，并继续把装机、利用小时、峰值负荷和储能/VPP供给弹性放在同一链路判断。
```

```yaml
signal:
  title: 可再生能源十五五规划首次量化可靠替代目标
  source: 国家发展改革委 《可再生能源发展“十五五”规划》答记者问
  source_url: https://www.ndrc.gov.cn/xxgk/jd/jd/202607/t20260723_1406645.html
  date: '2026-07-23'
  topic: policy
  layer: dispatch
  fact: 规划提出到2030年可再生能源发电总装机达到35亿千瓦左右，年发电量达到6万亿千瓦时左右；风电和太阳能发电总装机达到28亿千瓦以上，年发电量达到4万亿千瓦时以上；全国风电光伏平均置信出力达到8%，迎峰度夏度冬晚高峰风电光伏电量占比达到20%以上，“十五五”期间新增可再生能源可靠顶峰发电能力3亿千瓦以上。
strength: strong
confidence: high
impact: renewable_reliable_substitution 增强，说明政策关注点从装机规模上移到电量、容量支撑和系统调节能力，调度层和源网荷储协调的重要性提高。
next_action: 新增 renewable_reliable_substitution 指标，并在 energy-001 和 energy-002 中同时记录支持证据和供给弹性反证。
```

```yaml
signal:
  title: 6月绿证核发交易规模扩大
  source: 国家能源局 2026年6月全国可再生能源绿色电力证书核发及交易数据
  source_url: https://www.nea.gov.cn/20260724/d35b8a39fb724572b3d3ce3cbed9d4e9/c.html
  date: '2026-07-24'
  topic: policy
  layer: operations_knowledge
  fact: 2026年6月，国家能源局核发绿证3.73亿个，其中可交易绿证2.06亿个；全国交易绿证8273万个，其中绿色电力交易绿证4289万个，单独交易绿证3984万个。
strength: strong
confidence: high
impact: green_power_accounting 增强，绿证从核发口径进入交易口径，可能提高企业绿电采购、合规核算和能源数据工作流的重要性。
next_action: 更新 green_power_accounting、energy-003 和 EMS/operations_knowledge 候选；后续观察绿证是否进入企业高频采购、审计和用电管理流程。
```

```yaml
signal:
  title: 中国绿证价格指数正式发布
  source: 国家能源局 中国绿证价格指数
  source_url: https://www.nea.gov.cn/20260724/808ea736bb9741909dd46f8cb32ea0de/c.html
  date: '2026-07-24'
  topic: policy
  layer: operations_knowledge
  fact: 2026年6月，中国绿证价格指数收于181.0点，以2025年1月为基期100点，环比下跌0.2%，同比上涨23.2%；指数由国家发展和改革委员会价格监测中心、国家能源局电力业务资质管理中心联合编制。
strength: strong
confidence: high
impact: green_certificate_price_signal 增强，绿色属性开始具备连续、公开、可比较的价格观察口径。
next_action: 新增 green_certificate_price_signal 指标，并跟踪企业绿证采购、核销、审计和碳足迹管理是否形成持续工作流。
```

```yaml
signal:
  title: 上半年能源制造相关出口继续高增
  source: SCIO 2026 H1 China foreign trade briefing、Xinhua equipment manufacturing export update
  source_url: https://english.scio.gov.cn/pressroom/2026-07/14/content_118603461.html
  date: '2026-07-14'
  topic: energy_export
  layer: export_system
  fact: 2026年上半年，中国机电产品出口9.36万亿元，同比增长20.1%，占出口总值63.5%；装备制造业出口交货值同比增长18.2%，其中锂电池、风力发电机组和汽车出口分别同比增长37.6%、35.6%和65.3%。
strength: strong
confidence: high
impact: energy_equipment_export_orders 增强，说明能源制造外溢仍有规模和增速；但事实仍主要证明设备出口能力，不证明海外客户系统依赖。
next_action: 更新 energy-004 和 energy-export-system 候选，但置信度不因出口额上升而上调；下一步必须验证服务收入、软件绑定、运维网络和客户续约。
```
