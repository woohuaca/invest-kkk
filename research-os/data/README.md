# 数据采集层

## 结论

数据采集层用于记录能源行业事实和信号，不直接形成投资结论。每条信号必须服务一个问题：哪个电力产业层级正在获得复杂性控制权、瓶颈、定价权、数据优势或组织依赖？

## 数据流

```text
sources.md -> collection-log.md -> metrics/ 或 insights/ 或 hypotheses/ 或 control-rights/
```

## 采集对象

- 国家能源局。
- 国家电网。
- 电力市场改革文件。
- 储能政策、装机、利用率和商业模式。
- 数据中心负荷、能耗、并网和电力需求。

## 输出要求

- 记录事实来源和日期。
- 标注电力层级：`generation / transmission / distribution / dispatch / EMS / VPP / operations_knowledge`。
- 标注信号强度和置信度。
- 写出影响和下一步动作。
- 不输出股票推荐、买卖建议或交易动作。

## 使用方式

1. 从 `sources.md` 选择本周数据源。
2. 按 `schemas/weekly-signal.md` 记录 weekly signal。
3. 将信号写入 `collection-log.md`。
4. 能量化的信号进入 `metrics/`。
5. 能改变判断的信号进入 `insights/`。
6. 能验证或推翻假设的信号进入 `hypotheses/`。
7. 能指向控制点、瓶颈或定价权变化的信号进入 `control-rights/`。
