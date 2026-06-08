# 控制点评分卡

## 结论

控制点评分卡用于比较不同电力层级是否正在形成长期控制权。评分只用于研究优先级，不用于股票推荐。

## 评分表

| 候选控制点 | complexity_control | bottleneck_power | pricing_power | data_advantage | organizational_dependency | supply_response_lag | durability | confidence |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | --- |
| 稳定容量 | 3 | 4 | 3 | 1 | 2 | 4 | 3 | medium |
| 调度层 | 5 | 4 | 3 | 4 | 3 | 4 | 4 | medium |
| EMS | 4 | 3 | 3 | 4 | 5 | 3 | 4 | medium |
| 虚拟电厂 | 4 | 3 | 3 | 4 | 4 | 3 | 3 | medium |
| 运维知识 | 4 | 3 | 2 | 5 | 4 | 4 | 4 | low |

## 评分说明

- 1：弱。
- 2：偏弱。
- 3：中等。
- 4：强。
- 5：很强。

## 下一步

- 将高分候选写入 `candidates.md`。
- 用 `../metrics/` 和 `../hypotheses/` 校验评分。
- 对低置信度候选补充证据和反证。
