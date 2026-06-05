# 研究 Agents

## 结论

`agents/` 用来定义可重复执行的研究任务。Agent 的职责不是直接给出股票建议，而是稳定地产出信号、假设状态和控制点候选，供 `insights/` 和 `decisions/` 使用。

## Agent 流程

```text
Industry Observer -> Hypothesis Tracker -> Control Point Finder -> Insight Cards -> Decisions
```

## Agent 列表

| Agent | 文件 | 核心输出 | 频率 |
| --- | --- | --- | --- |
| Industry Observer | `industry-observer.md` | 行业信号 YAML | 每周 |
| Hypothesis Tracker | `hypothesis-tracker.md` | 假设状态更新 | 每周或有重大事实变化时 |
| Control Point Finder | `control-point-finder.md` | 控制点候选 | 每周或月度复盘 |

## 共同规则

- 只输出事实、信号、假设和判断，不直接推荐股票。
- 必须区分证据和反证。
- 必须记录置信度。
- 必须写出下一步动作。
- 如果信息不足，输出 `confidence: low`，不要强行下结论。
- 所有重要输出应能进入 `insights/` 的洞察卡片，或进入 `industries/energy/hypotheses.md` 的假设列表。

## 输出关系

- `Industry Observer` 发现外部变化。
- `Hypothesis Tracker` 判断这些变化验证、削弱还是推翻现有假设。
- `Control Point Finder` 判断变化是否说明新的瓶颈、控制点或组织依赖正在形成。
