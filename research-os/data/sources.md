# 数据源清单

## 结论

数据源清单用于约束每周采集范围，避免研究变成随机新闻摘抄。

## 核心数据源

| 数据源 | 关注内容 | 可能影响层级 | 输出去向 |
| --- | --- | --- | --- |
| 国家能源局 | 政策、装机、用电量、电力市场改革 | generation / dispatch / VPP | metrics / hypotheses / control-rights |
| 国家电网 | 电网投资、调度、并网、负荷、特高压 | transmission / distribution / dispatch | metrics / control-rights |
| 电力市场文件 | 现货、容量、辅助服务、需求响应 | dispatch / EMS / VPP | insights / hypotheses / control-rights |
| 储能 | 装机、利用率、价格、商业模式 | generation / dispatch / VPP | metrics / insights |
| 数据中心 | 负荷增长、能耗、并网、可靠性要求 | distribution / dispatch / EMS | metrics / control-rights |
| 朗新能源研究院「观价」 | 省级现货价格、日前-实时价差、燃煤基准价、一次能源、天气、供需预测、政策动态 | dispatch / EMS / VPP / operations_knowledge | data / metrics / insights / control-rights |

## 采集原则

- 优先官方和一手资料。
- 二手资料必须标注来源和不确定性。
- 机构研究源和公众号属于二级观察源，可用于发现价格、价差、预测和区域分化信号；关键事实必须回溯交易中心、监管机构或官方披露验证。
- 不把政策口号当作已发生事实。
- 不把短期价格波动当作行业信号。
- 每条数据必须说明它可能影响哪个电力层级。
