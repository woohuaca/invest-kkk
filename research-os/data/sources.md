# 数据源清单

## 结论

数据源清单用于约束每周采集范围，避免研究变成随机新闻摘抄。

## 核心数据源

| 数据源 | 关注内容 | 可能影响层级 | 输出去向 |
| --- | --- | --- | --- |
| 国家能源局 | 政策、装机、用电量、电力市场改革 | generation / dispatch / market | data / metrics / hypotheses |
| 国家电网 | 电网投资、调度、并网、负荷、特高压 | transmission / distribution / dispatch | data / metrics / control-rights |
| 电力市场文件 | 现货、容量、辅助服务、需求响应 | dispatch / EMS / VPP | insights / hypotheses / control-rights |
| 储能 | 装机、利用率、价格、商业模式 | generation / dispatch / VPP | metrics / insights |
| 数据中心 | 负荷增长、能耗、并网、可靠性要求 | distribution / dispatch / EMS | data / metrics / control-rights |

## 采集原则

- 优先官方和一手资料。
- 二手资料必须标注来源和不确定性。
- 不把政策口号当作已发生事实。
- 不把短期价格波动当作行业信号。
- 每条数据必须说明它可能影响哪个电力层级。
