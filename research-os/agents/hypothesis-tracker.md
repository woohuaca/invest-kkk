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
- 哪些判断需要转成洞察卡片、假设台账更新或控制点候选？

## 输入

- `hypotheses/hypothesis-ledger.md`
- `hypotheses/energy/power-control-rights.md`
- `insights/` 中的洞察卡片。
- `data/collection-log.md` 中的 weekly signal。
- `control-rights/candidates.md` 中的控制点候选。

## 处理流程

1. 列出当前活跃假设。
2. 为每条假设匹配新增证据和反证。
3. 判断状态：`active / verified / weakened / invalidated / resolved`。
4. 更新置信度，并记录变化原因。
5. 给出下一步动作：保留、上调、下调、重写、归档、更新洞察卡片或进入控制点候选。

## 输出格式

```yaml
hypothesis:
  id:
  title:
  statement:
  industry:
  scope:
status:
last_updated:
previous_confidence:
confidence:
confidence_change_reason:
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
- `last_updated`：本次更新日期，写入 `hypotheses/hypothesis-ledger.md`。
- `previous_confidence`：更新前置信度。
- `confidence`：更新后置信度，写入台账的当前 `confidence`。
- `confidence_change_reason`：置信度变化原因；如果没有变化，说明维持原因。
- `verified_by`：支持或验证假设的证据。
- `weakened_by`：削弱假设的证据。
- `invalidated_by`：推翻假设的证据。
- `decision_impact`：对研究判断、评分维度、观察优先级或风险判断的影响，不表示交易或仓位动作。
- `next_action`：下一步动作。

## 示例

```yaml
hypothesis:
  id: energy-001
  title: 稳定容量变得稀缺
  statement: 随着新能源渗透率提升，稳定电力容量的系统价值会上升。
  industry: 能源
  scope: 瓶颈 / 控制点
status: active
last_updated: '2026-06-05'
previous_confidence: 70%
confidence: 75%
confidence_change_reason: 新能源渗透率和高峰负荷调度复杂度继续上升，支持原假设。
verified_by:
  - 新能源渗透率持续提升。
  - 高峰负荷窗口的调度复杂度上升。
weakened_by:
  - 储能利用率提升速度快于预期。
invalidated_by: []
decision_impact: 提高可调度容量、EMS 和虚拟电厂控制层的研究优先级。
next_action: 保持 active，并更新相关 `insights/` 洞察卡片。
```

## 输出落点

- 假设状态写入 `hypotheses/hypothesis-ledger.md`。
- 电力控制权相关假设写入 `hypotheses/energy/power-control-rights.md`。
- 被验证、削弱或推翻的重要假设，应更新对应 `insights/` 洞察卡片。

## 禁止事项

- 不删除被推翻的假设；必须保留推翻原因。
- 不只记录支持证据。
- 不把置信度上调当作投资动作。
