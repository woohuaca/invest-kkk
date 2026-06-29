# 跟进策略

## 结论

跟进策略用于把每轮观察后的 `next_action` 收拢成可执行清单。它不是投资计划，也不是交易计划；它只回答下一轮研究要看什么、用什么来源验证、触发后更新哪个模块。

## 执行节奏

| 节奏 | 任务 | 输出 |
| --- | --- | --- |
| 每周 | 跑一次 `Industry Observer`，优先看官方数据、市场改革、储能、数据中心和二级观察源 | `data/collection-log.md` |
| 每周 | 把新增事实映射到指标和假设 | `metrics/calculation-log.md` / `hypotheses/hypothesis-ledger.md` |
| 每周 | 对本轮新增内容做 Review Gate | `reviews/` |
| 每月 | 比较控制点候选的证据、反证和评分 | `control-rights/` |
| 触发时 | 重大政策、市场规则、价格异常或新来源进入系统 | 新增或更新 review 记录 |

## 当前跟进看板

| 优先级 | 跟进项 | 观察指标 | 来源 | 状态 | 下一次动作 |
| --- | --- | --- | --- | --- | --- |
| P0 | 第三周能源观察 | renewable_penetration / capacity_utilization / charging_load_growth / demand_response / green_power_accounting | 国家能源局 | done_2026-06-29 | 下周继续观察迎峰度夏负荷、5月全社会用电量、现货市场正式运行和绿证数据核算落地 |
| P0 | 朗新能源「观价」连续观察 | day_ahead_realtime_spread / regional_price_divergence / market_volatility | 朗新能源研究院「观价」 | open | 连续观察至少两期，回溯交易中心或监管机构数据 |
| P0 | 电池材料价格回溯 | battery_material_price_index / storage_cost_pressure / resource_cycle_rebound | Benchmark Mineral Intelligence / Visual Capitalist / 大宗商品数据源 | open | 验证锂、钴、镍、天然石墨价格是否持续回升 |
| P0 | 储能供给弹性复核 | storage_cost_pressure / storage_utilization | 国家能源局、地方监管办、市场交易规则 | active | 将成本压力和利用小时放在同一链路判断，不单独使用材料价格 |
| P1 | 调度层控制权复核 | dispatch_market_reform / day_ahead_realtime_spread / congestion | 国家能源局、电力市场报告、交易中心 | active | 观察省级现货正式运行、实时市场 5 分钟出清和辅助服务市场推进 |
| P1 | VPP 控制权复核 | demand_response / storage_utilization / market_volatility | 电力市场报告、地方 VPP 试点、需求响应案例 | active | 区分理论调节能力、签约容量和实际调用收益 |
| P1 | 充电设施负荷与车网互动 | charging_load_growth / local_load_growth / demand_response / grid_connection_delay | 国家能源局、地方充电设施数据、VPP 试点 | active | 区分设施规模、实际充放电量、V2G 响应能力和调度收益 |
| P1 | 绿证与非化石电力消费核算 | green_power_accounting / data_feedback_loop / customer_switching_cost | 国家能源局、绿证交易平台、企业绿电采购案例 | active | 观察企业侧是否形成合规、采购、用电数据一体化工作流依赖 |
| P1 | 能源出口与绿色属性出海 | energy_equipment_export_orders / overseas_grid_capex / trade_barrier_policy / export_customer_dependency / green_power_accounting | 海关总署、商务部、IEA、海外电网投资、企业海外项目案例 | active | 区分设备出口、项目出口、系统出口和绿色属性出口，优先验证海外运维、软件和合规工作流 |
| P1 | 配网瓶颈复核 | grid_connection_delay / local_load_growth / congestion | 12398 通报、地方监管办、配网改造信息 | active | 跟踪低电压、台区承载力、新能源接入受限案例是否持续 |
| P2 | 数据中心组织依赖 | data_center_load_growth / customer_switching_cost / data_feedback_loop | 国家能源局、数据中心政策、客户案例 | open | 寻找客户工作流依赖、需求响应履约和数据反馈证据 |

## 触发规则

- 如果官方数据验证新能源渗透率、现货市场或容量机制继续增强，更新 `energy-001` 或 `energy-002`。
- 如果储能成本下降和利用率提升同时出现，降低稳定容量稀缺判断的置信度。
- 如果电池材料价格回升且储能利用率没有同步改善，强化调度层和 VPP 的 `supply_response_lag`。
- 如果 VPP 只有理论调节容量、缺少实际调用收益，不上调 VPP 或 EMS 的组织依赖评分。
- 如果充电设施和充放电电量高增，但缺少实际放电响应和收益数据，只增强配网/VPP 观察权重，不直接提高组织依赖判断。
- 如果绿证核算开始嵌入企业合规、采购和用电数据工作流，更新 `green_power_accounting`、`data_feedback_loop` 和 EMS / operations_knowledge 控制点。
- 如果能源出口只体现为设备出货增长但价格、毛利和服务收入承压，不上调控制权判断。
- 如果海外项目绑定 EMS/VPP、长期运维、绿电核算或客户合规流程，更新 `export_customer_dependency` 和能源出口控制点候选。
- 如果二级观察源出现强信号，先写入 `approved_with_limits`，再回溯一手数据源。

## Review Gate

每轮跟进后必须回答：

1. 本轮新增事实来自一手来源还是二级观察源？
2. 它增强、削弱、反证，还是新增了哪个变量？
3. 它更新了哪个指标？
4. 它是否改变假设置信度？
5. 它是否改变控制点候选？
6. 是否存在股票推荐、交易动作或仓位建议越界？
