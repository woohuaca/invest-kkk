# 洞察卡片

## 结论

`insights/` 的输出形式是洞察卡片。洞察卡片不是资料摘要，也不是投资决策，而是一个可证伪假设及其证据、反证、置信度、领先指标和下一步动作。

它位于研究信息流中间：

```text
observations/事实 -> insights/判断 -> decisions/动作
```

## 为什么重要

洞察卡片用于把分散事实转化为可追踪判断，避免研究停留在新闻、数据或叙事层。

一个好的洞察卡片必须能回答：

1. 当前假设是什么？
2. 支持它的证据是什么？
3. 哪些事实会削弱或推翻它？
4. 当前置信度是多少？
5. 应该跟踪哪些领先指标？
6. 下一步应更新观察、框架、评分，还是投资决策？

## 标准字段

```md
# Insight: <title>

title:
date:
industry:
scope:
status:
confidence:

## hypothesis

## evidence

## counter_evidence

## leading_indicators

## decision_impact

## next_action
```

## 字段说明

- `title`：一句话写清楚洞察，不写宽泛主题。
- `date`：记录首次形成该洞察的日期。
- `industry`：所属行业，例如 `Energy`。
- `scope`：洞察作用层级，例如 `Macro / Industry / Bottleneck / Control Point / Company / Timing`。
- `status`：当前状态，使用 `active / weakened / invalidated / resolved`。
- `confidence`：当前置信度，可以用百分比，也可以用 `高 / 中 / 低`。
- `hypothesis`：可证伪假设。
- `evidence`：支持该假设的事实，使用 bullet。
- `counter_evidence`：可能削弱或推翻该假设的事实，使用 bullet。
- `leading_indicators`：领先指标或复盘触发条件。
- `decision_impact`：说明它影响公司评分、观察名单、仓位判断、风险判断，还是只影响框架。
- `next_action`：下一步动作，必须具体到要看什么、更新什么或比较什么。

## 示例

```md
# Insight: Stable Capacity Becomes Scarce

title: Stable Capacity Becomes Scarce
date: 2026-06-05
industry: Energy
scope: Bottleneck / Control Point
status: active
confidence: 70%

## hypothesis

Stable power capacity will become more valuable as renewable penetration rises.

## evidence

- Wind and solar output are intermittent.
- Higher renewable penetration increases grid balancing complexity.
- Dispatchable capacity may gain value when reliability becomes scarce.

## counter_evidence

- Storage costs may decline rapidly.
- Grid flexibility may improve through demand response.
- Policy may cap returns for capacity providers.

## leading_indicators

- Capacity market policy
- Storage utilization
- Peak-hour power price spreads
- Curtailment rate
- Dispatch market reform

## decision_impact

Increase research weight on companies that control dispatchable capacity, EMS, storage coordination, or power dispatch infrastructure.

## next_action

Track dispatch market reform and compare companies across generation, dispatch, EMS, and virtual power plant layers.
```

## 使用原则

- 一张卡片只表达一个洞察。
- 证据和反证都必须写，不能只写支持材料。
- `confidence` 可以调整，调整时应保留新日期和原因。
- 洞察不能直接等于买入或卖出建议，必须先进入 `decisions/` 才能形成投资动作。
