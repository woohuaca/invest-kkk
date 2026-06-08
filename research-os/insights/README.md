# 洞察卡片

## 结论

`insights/` 的输出形式是洞察卡片。洞察卡片不是资料摘要，也不是投资决策，而是一个可证伪假设及其证据、反证、置信度、领先指标和下一步动作。

它位于研究信息流中间：

```text
observations/事实 -> insights/判断 -> 研究优先级 / 假设跟踪 / 控制权分析
```

## 为什么重要

洞察卡片用于把分散事实转化为可追踪判断，避免研究停留在新闻、数据或叙事层。

一个好的洞察卡片必须能回答：

1. 当前假设是什么？
2. 支持它的证据是什么？
3. 哪些事实会削弱或推翻它？
4. 当前置信度是多少？
5. 应该跟踪哪些领先指标？
6. 下一步应更新观察、指标、框架、控制点评分，还是假设跟踪？

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
- `decision_impact`：在 v0.1 中表示研究决策影响，说明它如何影响研究优先级、假设跟踪、候选控制点、控制权分析、指标观察或框架更新；不表示交易动作、股票推荐或仓位建议。
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

稳定电力容量会随着新能源渗透率提升而变得更有系统价值。

## evidence

- 风电和光伏出力具有间歇性。
- 新能源渗透率越高，电网平衡复杂性越高。
- 当可靠性变稀缺时，可调容量可能获得更高系统价值。
- 电力市场改革可能让可靠性和平衡价值显性定价。

## counter_evidence

- 储能成本可能快速下降。
- 需求响应可能提升电网灵活性。
- 政策可能限制容量提供方的收益。
- 地方市场规则可能延迟可靠性价值的定价。

## leading_indicators

- 容量市场政策。
- 储能利用率。
- 峰时电价价差。
- 弃风弃光率。
- 调度市场改革。

## decision_impact

提高对稳定容量、调度、EMS、储能协调和电力调度基础设施等层级和资产类型的研究权重。

## next_action

跟踪调度市场改革，并在 `control-rights/control-point-scorecard.md` 中比较 generation、dispatch、EMS、VPP 和 operations_knowledge 层级。
```

## 示例文件

- `examples/stable-capacity-becomes-scarce.md`：展示“稳定容量变稀缺”如何从数据采集、指标判断进入洞察卡片。

## 使用原则

- 一张卡片只表达一个洞察。
- 证据和反证都必须写，不能只写支持材料。
- `confidence` 可以调整，调整时应保留新日期和原因。
- 洞察卡片不输出交易动作、股票推荐或仓位建议；在 v0.1 中，它只用于决定研究优先级、假设跟踪、候选控制点和控制权分析的下一步。
