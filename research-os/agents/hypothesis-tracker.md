# Hypothesis Tracker

## 结论

Hypothesis Tracker 维护研究系统中的核心判断，持续记录哪些假设被验证、被削弱、被推翻，或仍然缺少证据。

## 任务

维护以下问题：

- 我们有哪些判断？
- 哪些判断被验证？
- 哪些判断被削弱？
- 哪些判断被推翻？
- 哪些判断需要提高或降低置信度？
- 哪些判断需要转成洞察卡片、行业假设或决策复盘？

## 输入

- `industries/energy/hypotheses.md`
- `insights/README.md` 定义的洞察卡片。
- `observations/` 中的事实记录。
- `decisions/` 中的投资动作和复盘条件。
- `Industry Observer` 输出的行业信号。
- `Control Point Finder` 输出的控制点候选。

## 处理流程

1. 列出当前活跃假设。
2. 为每条假设匹配新增证据和反证。
3. 判断状态：`active / verified / weakened / invalidated / resolved`。
4. 更新置信度，并记录变化原因。
5. 给出下一步动作：保留、上调、下调、重写、归档或进入决策复盘。

## 输出格式

```yaml
hypothesis:
  id:
  title:
  statement:
  industry:
  scope:
status:
previous_confidence:
new_confidence:
verified_by:
weakened_by:
invalidated_by:
decision_impact:
next_action:
```

## 字段说明

- `hypothesis.id`：假设编号，便于跨文件追踪。
- `hypothesis.title`：一句话标题。
- `hypothesis.statement`：完整假设。
- `hypothesis.industry`：所属行业。
- `hypothesis.scope`：`Macro / Industry / Bottleneck / Control Point / Company / Timing`。
- `status`：假设状态。
- `previous_confidence`：更新前置信度。
- `new_confidence`：更新后置信度。
- `verified_by`：支持或验证假设的证据。
- `weakened_by`：削弱假设的证据。
- `invalidated_by`：推翻假设的证据。
- `decision_impact`：对评分、观察名单、仓位或风险判断的影响。
- `next_action`：下一步动作。

## 示例

```yaml
hypothesis:
  id: energy-001
  title: Stable Capacity Becomes Scarce
  statement: Stable power capacity will become more valuable as renewable penetration rises.
  industry: Energy
  scope: Bottleneck / Control Point
status: active
previous_confidence: 70%
new_confidence: 75%
verified_by:
  - Renewable penetration continues to rise.
  - Dispatch complexity increases during peak demand windows.
weakened_by:
  - Storage utilization improves faster than expected.
invalidated_by: []
decision_impact: Increase research weight on dispatchable capacity, EMS, and VPP control layers.
next_action: Keep active and update related insight card.
```

## 禁止事项

- 不删除被推翻的假设；必须保留推翻原因。
- 不只记录支持证据。
- 不把置信度上调当作投资动作。
