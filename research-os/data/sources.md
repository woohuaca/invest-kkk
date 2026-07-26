# 数据源清单

## 结论

数据源清单用于约束每周采集范围，避免研究变成随机新闻摘抄。

## 核心数据源

| 数据源 | 关注内容 | 可能影响层级 | 输出去向 |
| --- | --- | --- | --- |
| 国家能源局 | 政策、装机、用电量、电力市场改革 | generation / dispatch / VPP | metrics / hypotheses / control-rights |
| 12398能源监管热线 | 投诉举报、低电压、停电、并网、调度指令执行和监管整改 | distribution / dispatch / EMS | data / metrics / control-rights / reviews |
| 国家发展改革委/国家能源局规划解读 | 可再生能源中长期目标、可靠替代、系统调节和市场机制 | generation / dispatch / VPP | data / metrics / hypotheses / control-rights |
| 国家电网 | 电网投资、调度、并网、负荷、特高压 | transmission / distribution / dispatch | metrics / control-rights |
| 电力市场文件 | 现货、容量、辅助服务、需求响应 | dispatch / EMS / VPP | insights / hypotheses / control-rights |
| 储能 | 装机、利用率、价格、商业模式 | generation / dispatch / VPP | metrics / insights |
| 数据中心 | 负荷增长、能耗、并网、可靠性要求 | distribution / dispatch / EMS | metrics / control-rights |
| 中国绿证价格指数 | 绿证价格、交易趋势、绿色属性定价 | EMS / operations_knowledge | data / metrics / hypotheses / control-rights |
| 能源数据安全与分级文件 | 能源数据分类分级、重要数据、核心数据、实时控制指令和电力消费数据 | EMS / operations_knowledge | data / metrics / hypotheses / control-rights |
| NIST / OT 安全资料 | 工业控制系统、OT 安全边界、边缘控制、云/AI/数字孪生进入 OT 环境 | EMS / VPP / operations_knowledge | data / metrics / hypotheses / control-rights |
| OT 暴露面研究 | 公网可访问 OT 设备、工业协议、HMI/SCADA 暴露、攻击面变化 | EMS / VPP / operations_knowledge | data / metrics / hypotheses / control-rights |
| 朗新能源研究院「观价」 | 省级现货价格、日前-实时价差、燃煤基准价、一次能源、天气、供需预测、政策动态 | dispatch / EMS / VPP / operations_knowledge | data / metrics / insights / control-rights |
| REAI Lab「从图说起」 | 电池材料价格、储能上游资源周期、供应链再定价 | generation / VPP / dispatch | data / metrics / hypotheses / control-rights |

## 采集原则

- 优先官方和一手资料。
- 二手资料必须标注来源和不确定性。
- 机构研究源和公众号属于二级观察源，可用于发现价格、价差、预测和区域分化信号；关键事实必须回溯交易中心、监管机构或官方披露验证。
- 不把政策口号当作已发生事实。
- 不把短期价格波动当作行业信号。
- 每条数据必须说明它可能影响哪个电力层级。
