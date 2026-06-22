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
