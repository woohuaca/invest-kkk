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
