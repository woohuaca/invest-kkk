# 指标计算层

## 结论

指标计算层把事实转成可比较指标，用于判断哪个电力产业层级正在形成瓶颈、定价权、数据优势或组织依赖。

## 非目标

- 不建立复杂量化模型。
- 不输出交易信号。
- 不输出股票推荐。

## 指标类型

- 增长指标。
- 供给响应指标。
- 瓶颈指标。
- 控制权指标。
- 政策指标。

## 使用方式

1. 从数据采集层 `data/collection-log.md` 选择信号。
2. 在指标计算层 `metric-catalog.md` 找到对应指标。
3. 在指标计算层 `power-layer-metrics.md` 判断指标对应的电力层级。
4. 在指标计算层 `calculation-log.md` 记录本次判断。
5. 如果指标改变控制权判断，更新控制权分析模块 `control-rights/control-point-scorecard.md` 或 `control-rights/candidates.md`。
6. 如果指标形成可验证判断，更新洞察卡片 `insights/`；如果改变待验证命题，更新假设跟踪系统 `hypotheses/hypothesis-ledger.md`。
