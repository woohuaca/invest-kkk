# 研究 Agents

## 结论

`agents/` 用来定义可重复执行的研究任务。Agent 的职责不是直接给出股票建议，而是稳定地产出信号、指标判断、假设状态和控制点候选，供 `data/`、`metrics/`、`insights/`、`hypotheses/` 和 `control-rights/` 使用。

## Agent 流程

```text
Industry Observer -> data/ -> metrics/ -> insights/ -> hypotheses/ -> control-rights/ -> Research Reviewer -> reviews/
```

Agent 不直接输出股票推荐、交易动作或仓位建议。

## Agent 列表

| Agent | 文件 | 核心输出 | 频率 |
| --- | --- | --- | --- |
| Industry Observer | `industry-observer.md` | 行业信号 YAML | 每周 |
| Hypothesis Tracker | `hypothesis-tracker.md` | 假设状态更新 | 每周或有重大事实变化时 |
| Control Point Finder | `control-point-finder.md` | 控制点候选 | 每周或月度复盘 |
| Research Reviewer | `research-reviewer.md` | 研究评审记录 | 每轮观察后 |

## 共同规则

- 只输出事实、信号、假设和判断，不直接推荐股票。
- 必须区分证据和反证。
- 必须记录置信度。
- 必须写出下一步动作。
- 如果信息不足，输出 `confidence: low`，不要强行下结论。
- 所有重要输出应能进入 `insights/` 的洞察卡片，或进入 `hypotheses/hypothesis-ledger.md` 的假设台账。

## 输出关系

- `Industry Observer` 发现外部变化。
- `Hypothesis Tracker` 判断这些变化验证、削弱还是推翻现有假设。
- `Control Point Finder` 判断变化是否说明新的瓶颈、控制点或组织依赖正在形成。
- `Research Reviewer` 检查事实可追溯性、schema、推理链、反证和研究边界。

## 输出落点

- `Industry Observer` 的 weekly signal 写入 `data/collection-log.md`。
- `Hypothesis Tracker` 的状态更新写入 `hypotheses/hypothesis-ledger.md`。
- `Control Point Finder` 的候选控制点写入 `control-rights/candidates.md`。
- 能改变判断的输出应同步形成 `insights/` 洞察卡片。
- `Research Reviewer` 的评审记录写入 `reviews/`。
