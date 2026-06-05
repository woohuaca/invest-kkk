# Energy Research OS v0.1 Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a pure Markdown Energy Research OS v0.1 that identifies future 10-year control-right assets in the power industry without trading or stock recommendation functionality.

**Architecture:** The implementation adds five research modules under `research-os/`: `data/`, `metrics/`, `insights/`, `hypotheses/`, and `control-rights/`. Existing agents remain the execution layer and are updated to write outputs into those modules. The system is manual-first and script-ready, with structured schemas and logs but no automation code.

**Tech Stack:** Markdown, YAML-shaped schemas inside Markdown, Git verification commands. No runtime, crawler, database, Web UI, trading logic, or stock recommendation code is added.

---

## File Structure

Create:

- `/Users/woohuaca/Documents/invest-kkk/research-os/data/README.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/data/sources.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/data/collection-log.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/data/schemas/weekly-signal.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/metrics/README.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/metrics/metric-catalog.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/metrics/power-layer-metrics.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/metrics/calculation-log.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/insights/examples/stable-capacity-becomes-scarce.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/hypotheses/README.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/hypotheses/hypothesis-ledger.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/hypotheses/energy/power-control-rights.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/control-rights/README.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/control-rights/power-layer-map.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/control-rights/control-point-scorecard.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/control-rights/candidates.md`

Modify:

- `/Users/woohuaca/Documents/invest-kkk/research-os/AGENTS.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/agents/README.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/agents/industry-observer.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/agents/hypothesis-tracker.md`
- `/Users/woohuaca/Documents/invest-kkk/research-os/agents/control-point-finder.md`

## Task 1: Data Collection Layer

**Files:**
- Create: `research-os/data/README.md`
- Create: `research-os/data/sources.md`
- Create: `research-os/data/collection-log.md`
- Create: `research-os/data/schemas/weekly-signal.md`

- [ ] **Step 1: Create data directories**

Run:

```bash
mkdir -p research-os/data/schemas
```

Expected: command exits with status `0`.

- [ ] **Step 2: Create `research-os/data/README.md`**

Write:

```md
# 数据采集层

## 结论

数据采集层用于记录能源行业事实和信号，不直接形成投资结论。每条信号必须服务一个问题：哪个电力产业层级正在获得复杂性控制权、瓶颈、定价权、数据优势或组织依赖？

## 数据流

```text
sources.md -> collection-log.md -> metrics/ 或 insights/ 或 hypotheses/
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
```

- [ ] **Step 3: Create `research-os/data/sources.md`**

Write:

```md
# 数据源清单

## 结论

数据源清单用于约束每周采集范围，避免研究变成随机新闻摘抄。

## 核心数据源

| 数据源 | 关注内容 | 可能影响层级 | 输出去向 |
| --- | --- | --- | --- |
| 国家能源局 | 政策、装机、用电量、电力市场改革 | generation / dispatch / market | data / metrics / hypotheses |
| 国家电网 | 电网投资、调度、并网、负荷、特高压 | transmission / distribution / dispatch | data / metrics / control-rights |
| 电力市场文件 | 现货、容量、辅助服务、需求响应 | dispatch / EMS / VPP | insights / hypotheses / control-rights |
| 储能 | 装机、利用率、价格、商业模式 | generation / dispatch / VPP | metrics / insights |
| 数据中心 | 负荷增长、能耗、并网、可靠性要求 | distribution / dispatch / EMS | data / metrics / control-rights |

## 采集原则

- 优先官方和一手资料。
- 二手资料必须标注来源和不确定性。
- 不把政策口号当作已发生事实。
- 不把短期价格波动当作行业信号。
- 每条数据必须说明它可能影响哪个电力层级。
```

- [ ] **Step 4: Create `research-os/data/schemas/weekly-signal.md`**

Write:

```md
# Weekly Signal Schema

## 结论

Weekly signal 是数据采集层的最小输出单位。它记录事实、信号强度、置信度、影响和下一步动作。

## Schema

```yaml
signal:
  title:
  source:
  date:
  topic:
  layer:
  fact:
strength:
confidence:
impact:
next_action:
```

## 字段说明

- `signal.title`：一句话信号标题。
- `signal.source`：信息来源。
- `signal.date`：事实日期或发布日期。
- `signal.topic`：`policy / grid / power_market / storage / data_center / dispatch`。
- `signal.layer`：`generation / transmission / distribution / dispatch / EMS / VPP / operations_knowledge`。
- `signal.fact`：事实本身，不写推断。
- `strength`：`weak / medium / strong`。
- `confidence`：`low / medium / high` 或百分比。
- `impact`：该事实可能影响的瓶颈、控制点、指标或假设。
- `next_action`：下一步进入 `metrics/`、`insights/`、`hypotheses/` 或 `control-rights/`。

## 示例

```yaml
signal:
  title: Dispatch reform increases value of stable capacity
  source: Power market reform document
  date: 2026-06-05
  topic: power_market
  layer: dispatch
  fact: Market rules increasingly price reliability and balancing capacity.
strength: medium
confidence: medium
impact: Stable capacity and dispatch capability may become more visible control points.
next_action: Update metrics/power-layer-metrics.md and insights/examples/stable-capacity-becomes-scarce.md.
```
```

- [ ] **Step 5: Create `research-os/data/collection-log.md`**

Write:

```md
# 数据采集日志

## 结论

本文件记录每周能源行业信号。所有记录必须符合 `schemas/weekly-signal.md`。

## 2026-06-05

```yaml
signal:
  title: Stable capacity may become more scarce
  source: Energy Research OS v0.1 seed
  date: 2026-06-05
  topic: power_market
  layer: dispatch
  fact: Higher renewable penetration increases the need for reliable capacity and balancing.
strength: medium
confidence: medium
impact: Supports the hypothesis that stable capacity and dispatch capability may become control points.
next_action: Link to insights/examples/stable-capacity-becomes-scarce.md and hypotheses/hypothesis-ledger.md.
```
```

- [ ] **Step 6: Verify data layer**

Run:

```bash
find research-os/data -type f -print
rg -n "Weekly Signal|signal:|strength:|confidence:|impact:|next_action:|generation / transmission / distribution / dispatch / EMS / VPP / operations_knowledge" research-os/data
```

Expected: four data files exist, and the schema fields are found.

- [ ] **Step 7: Commit data layer**

Run:

```bash
git add research-os/data
git commit -m "docs: add energy data collection layer"
```

Expected: commit succeeds.

## Task 2: Metrics Layer

**Files:**
- Create: `research-os/metrics/README.md`
- Create: `research-os/metrics/metric-catalog.md`
- Create: `research-os/metrics/power-layer-metrics.md`
- Create: `research-os/metrics/calculation-log.md`

- [ ] **Step 1: Create metrics directory**

Run:

```bash
mkdir -p research-os/metrics
```

Expected: command exits with status `0`.

- [ ] **Step 2: Create `research-os/metrics/README.md`**

Write:

```md
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

1. 从 `data/collection-log.md` 选择信号。
2. 在 `metric-catalog.md` 找到对应指标。
3. 在 `power-layer-metrics.md` 判断指标对应的电力层级。
4. 在 `calculation-log.md` 记录本次判断。
5. 如果指标改变判断，更新 `insights/` 或 `hypotheses/`。
```

- [ ] **Step 3: Create `research-os/metrics/metric-catalog.md`**

Write:

```md
# 指标目录

## 结论

指标目录定义 v0.1 使用的能源研究指标。每个指标必须说明口径、解释方式和控制权含义。

| 指标 | 类型 | 口径 | 控制权含义 | 使用限制 |
| --- | --- | --- | --- | --- |
| renewable_penetration | 增长指标 | 新能源发电量或装机占比 | 渗透率越高，系统调度复杂性越高 | 不能单独证明稳定容量稀缺 |
| data_center_load_growth | 增长指标 | 数据中心负荷或用电需求增速 | 高可靠负荷可能改变配电和调度瓶颈 | 需区分规划和实际投运 |
| capacity_utilization | 瓶颈指标 | 可调容量利用率或紧张程度 | 高利用率可能说明稳定容量稀缺 | 需结合电力市场规则 |
| peak_valley_spread | 瓶颈指标 | 峰谷电价差或现货价差 | 价差扩大可能反映调节资源价值 | 受政策定价影响 |
| grid_connection_delay | 供给响应指标 | 并网等待和项目延期 | 并网慢可能说明电网或调度成为瓶颈 | 需区分区域差异 |
| storage_utilization | 供给响应指标 | 储能调用频率和利用小时 | 高利用率可能验证储能或调度价值 | 低利用率可能来自规则未成熟 |
| dispatch_market_reform | 政策指标 | 现货、辅助服务、容量机制进展 | 系统价值显性定价可能提升调度层价值 | 政策落地速度不确定 |
| customer_switching_cost | 控制权指标 | 客户替换系统、流程和数据迁移难度 | 高切换成本支持组织依赖 | 需要客户案例验证 |
| data_feedback_loop | 控制权指标 | 数据积累是否改善预测、调度或运维 | 数据反馈越强，知识层控制权越强 | 需证明数据能转化为定价权 |
```

- [ ] **Step 4: Create `research-os/metrics/power-layer-metrics.md`**

Write:

```md
# 电力层级指标

## 结论

指标必须映射到电力产业层级。v0.1 关注的层级是发电、输电、配电、调度、EMS、虚拟电厂和运维知识。

| 层级 | 核心问题 | 关键指标 | 控制权判断 |
| --- | --- | --- | --- |
| generation | 稳定容量是否变稀缺 | renewable_penetration / capacity_utilization | 可调容量可能获得更高系统价值 |
| transmission | 输电能力是否成为瓶颈 | grid_connection_delay / congestion | 输电约束可能转移利润池 |
| distribution | 配电侧复杂性是否上升 | data_center_load_growth / local_load_growth | 高可靠负荷可能提高配电侧控制权 |
| dispatch | 调度是否控制复杂性 | peak_valley_spread / dispatch_market_reform | 调度层可能获得显性定价权 |
| EMS | 客户是否依赖能源管理系统 | customer_switching_cost / data_feedback_loop | EMS 可能形成组织依赖 |
| VPP | 聚合能力是否变成控制点 | storage_utilization / demand_response | 虚拟电厂价值取决于调度和客户依赖 |
| operations_knowledge | 运维知识是否可复制 | data_feedback_loop / customer_retention | 知识层可能沉淀长期控制权 |
```

- [ ] **Step 5: Create `research-os/metrics/calculation-log.md`**

Write:

```md
# 指标计算日志

## 结论

本文件记录每次指标判断如何得出。v0.1 不追求复杂模型，只要求口径清楚、解释克制、能支持或反证假设。

## 2026-06-05

### renewable_penetration

- 来源：Energy Research OS v0.1 seed。
- 观察：新能源渗透率提升会增加系统平衡需求。
- 指标判断：该指标支持关注 `dispatch` 和 `stable capacity`。
- 反证：如果储能成本快速下降并充分利用，稳定容量稀缺可能下降。
- 下一步：进入 `insights/examples/stable-capacity-becomes-scarce.md`。
```

- [ ] **Step 6: Verify metrics layer**

Run:

```bash
find research-os/metrics -type f -print
rg -n "renewable_penetration|data_center_load_growth|capacity_utilization|dispatch_market_reform|customer_switching_cost|data_feedback_loop|generation|dispatch|EMS|VPP" research-os/metrics
```

Expected: four metrics files exist, and key metrics are found.

- [ ] **Step 7: Commit metrics layer**

Run:

```bash
git add research-os/metrics
git commit -m "docs: add energy metrics layer"
```

Expected: commit succeeds.

## Task 3: Insight Card Example

**Files:**
- Create: `research-os/insights/examples/stable-capacity-becomes-scarce.md`
- Modify: `research-os/insights/README.md`

- [ ] **Step 1: Create insights examples directory**

Run:

```bash
mkdir -p research-os/insights/examples
```

Expected: command exits with status `0`.

- [ ] **Step 2: Create `research-os/insights/examples/stable-capacity-becomes-scarce.md`**

Write:

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
- Power market reform may make reliability and balancing value more explicit.

## counter_evidence

- Storage costs may decline rapidly.
- Grid flexibility may improve through demand response.
- Policy may cap returns for capacity providers.
- Local market rules may delay pricing of reliability value.

## leading_indicators

- Capacity market policy.
- Storage utilization.
- Peak-hour power price spreads.
- Curtailment rate.
- Dispatch market reform.

## decision_impact

Increase research weight on layers and asset types that control stable capacity, dispatch, EMS, storage coordination, or power dispatch infrastructure.

## next_action

Track dispatch market reform and compare generation, dispatch, EMS, VPP, and operations knowledge layers in `control-rights/control-point-scorecard.md`.
```

- [ ] **Step 3: Update `research-os/insights/README.md`**

Add this section after the example code block and before `## 使用原则`:

```md
## 示例文件

- `examples/stable-capacity-becomes-scarce.md`：展示“稳定容量变稀缺”如何从数据采集、指标判断进入洞察卡片。
```

- [ ] **Step 4: Verify insight card system**

Run:

```bash
find research-os/insights -type f -print
rg -n "Stable Capacity Becomes Scarce|counter_evidence|leading_indicators|decision_impact|examples/stable-capacity-becomes-scarce.md" research-os/insights
```

Expected: README and example file exist, and required fields are found.

- [ ] **Step 5: Commit insight example**

Run:

```bash
git add research-os/insights
git commit -m "docs: add energy insight card example"
```

Expected: commit succeeds.

## Task 4: Hypothesis Tracking System

**Files:**
- Create: `research-os/hypotheses/README.md`
- Create: `research-os/hypotheses/hypothesis-ledger.md`
- Create: `research-os/hypotheses/energy/power-control-rights.md`

- [ ] **Step 1: Create hypotheses directories**

Run:

```bash
mkdir -p research-os/hypotheses/energy
```

Expected: command exits with status `0`.

- [ ] **Step 2: Create `research-os/hypotheses/README.md`**

Write:

```md
# 假设跟踪系统

## 结论

假设跟踪系统维护 Research OS 的核心判断，记录哪些假设被验证、削弱、推翻或解决。

## 状态

- `active`：仍在观察。
- `verified`：被关键证据验证。
- `weakened`：被反证削弱。
- `invalidated`：被推翻。
- `resolved`：已完成研究闭环。

## 使用方式

1. 从 `insights/` 或 `data/` 识别需要跟踪的假设。
2. 写入 `hypothesis-ledger.md`。
3. 重大行业变化时更新状态和置信度。
4. 被推翻的假设不得删除，必须保留反证原因。
5. 可影响控制权判断的假设进入 `energy/power-control-rights.md`。
```

- [ ] **Step 3: Create `research-os/hypotheses/hypothesis-ledger.md`**

Write:

```md
# 假设台账

## 结论

本文件记录 Energy Research OS v0.1 的核心假设。每条假设必须包含状态、置信度、证据、反证和下一步动作。

## Hypothesis: energy-001

```yaml
hypothesis:
  id: energy-001
  title: Stable Capacity Becomes Scarce
  statement: Stable power capacity will become more valuable as renewable penetration rises.
  scope: Bottleneck / Control Point
status: active
confidence: 70%
supporting_evidence:
  - Higher renewable penetration increases balancing complexity.
  - Power market reform may price reliability more explicitly.
counter_evidence:
  - Storage costs may decline rapidly.
  - Demand response may reduce stable capacity scarcity.
linked_insights:
  - insights/examples/stable-capacity-becomes-scarce.md
linked_metrics:
  - renewable_penetration
  - capacity_utilization
  - peak_valley_spread
next_action: Track dispatch market reform and storage utilization.
```

## Hypothesis: energy-002

```yaml
hypothesis:
  id: energy-002
  title: Dispatch Layer Gains Complexity Control
  statement: The dispatch layer may gain more long-term control rights than standalone generation assets.
  scope: Control Point
status: active
confidence: 60%
supporting_evidence:
  - Distributed generation and flexible loads increase system complexity.
counter_evidence:
  - Grid operators or regulators may cap commercial capture of dispatch value.
linked_insights: []
linked_metrics:
  - dispatch_market_reform
  - peak_valley_spread
next_action: Compare dispatch, EMS, and VPP control layers.
```

## Hypothesis: energy-003

```yaml
hypothesis:
  id: energy-003
  title: EMS Value Depends on Organizational Dependency
  statement: EMS and VPP value depends on organizational dependency, not just aggregated capacity.
  scope: Control Point / Company
status: active
confidence: 60%
supporting_evidence:
  - Energy systems become harder to manage manually as distributed assets grow.
counter_evidence:
  - EMS may commoditize if switching costs remain low.
linked_insights: []
linked_metrics:
  - customer_switching_cost
  - data_feedback_loop
next_action: Find customer workflow evidence for EMS dependency.
```
```

- [ ] **Step 4: Create `research-os/hypotheses/energy/power-control-rights.md`**

Write:

```md
# 电力控制权假设

## 结论

未来 10 年电力产业控制权可能从单一资产拥有，逐步上移到稳定容量、调度、EMS、虚拟电厂和运维知识层。

## 初始假设

1. 稳定容量会随着新能源渗透率提升而变稀缺。
2. 调度层比单一发电资产更可能获得复杂性控制权。
3. EMS 和虚拟电厂的价值取决于组织依赖，而不只是聚合容量。
4. 数据中心负荷增长会改变电力系统瓶颈位置。
5. 电力市场改革会把隐性系统价值显性定价。

## 反证方向

- 储能成本快速下降并充分消除容量稀缺。
- 电力市场改革迟缓，系统价值无法显性定价。
- EMS 和 VPP 产品无法形成客户切换成本。
- 电网或监管主体吸收大部分调度价值。

## 下一步观察

- 更新 `hypothesis-ledger.md`。
- 将强假设转成 `insights/` 卡片。
- 将可评分假设输入 `control-rights/control-point-scorecard.md`。
```

- [ ] **Step 5: Verify hypothesis system**

Run:

```bash
find research-os/hypotheses -type f -print
rg -n "energy-001|Stable Capacity Becomes Scarce|active|verified|weakened|invalidated|resolved|supporting_evidence|counter_evidence|未来 10 年电力产业控制权" research-os/hypotheses
```

Expected: three hypothesis files exist, and status/schema fields are found.

- [ ] **Step 6: Commit hypothesis system**

Run:

```bash
git add research-os/hypotheses
git commit -m "docs: add energy hypothesis tracking system"
```

Expected: commit succeeds.

## Task 5: Control Rights Analysis Module

**Files:**
- Create: `research-os/control-rights/README.md`
- Create: `research-os/control-rights/power-layer-map.md`
- Create: `research-os/control-rights/control-point-scorecard.md`
- Create: `research-os/control-rights/candidates.md`

- [ ] **Step 1: Create control-rights directory**

Run:

```bash
mkdir -p research-os/control-rights
```

Expected: command exits with status `0`.

- [ ] **Step 2: Create `research-os/control-rights/README.md`**

Write:

```md
# 控制权分析模块

## 结论

控制权分析模块用于识别未来 10 年电力产业控制权资产。它输出控制点候选，不输出股票推荐、交易动作或仓位建议。

## 分析顺序

```text
电力层级 -> 控制点 -> 资产类型 -> 证据 -> 反证 -> 置信度 -> 下一步动作
```

## 评分维度

- `complexity_control`：是否控制复杂性。
- `bottleneck_power`：是否成为瓶颈。
- `pricing_power`：是否获得定价权。
- `data_advantage`：是否沉淀数据优势。
- `organizational_dependency`：是否形成组织依赖。
- `supply_response_lag`：供给响应是否慢。
- `durability`：控制权是否能持续 10 年。

## 禁止事项

- 不输出买入、卖出、加仓、减仓或仓位建议。
- 不把增长最快直接等同于最有价值。
- 不把资源拥有直接等同于控制点。
```

- [ ] **Step 3: Create `research-os/control-rights/power-layer-map.md`**

Write:

```md
# 电力产业层级地图

## 结论

电力产业控制权分析必须先看层级，再看公司。v0.1 的核心层级是发电、输电、配电、调度、EMS、虚拟电厂和运维知识。

| 层级 | 核心资产 | 复杂性来源 | 可能控制点 |
| --- | --- | --- | --- |
| 发电 | 稳定容量、新能源、储能 | 出力波动、容量可靠性 | 可调容量、低成本资源 |
| 输电 | 主网、特高压、跨区通道 | 区域供需错配、拥塞 | 输电通道、调度规则 |
| 配电 | 配网、园区、电力接入 | 分布式资产和高可靠负荷 | 接入能力、局部负荷管理 |
| 调度 | 现货、辅助服务、容量机制 | 多资产实时平衡 | 调度算法、市场规则 |
| EMS | 工商业能源管理系统 | 多设备、多目标优化 | 客户工作流、数据闭环 |
| 虚拟电厂 | 聚合资源、需求响应 | 分布式资源协调 | 聚合调度能力 |
| 运维知识 | 运行经验、预测模型、数据 | 经验沉淀和复制 | 知识库、模型、组织流程 |
```

- [ ] **Step 4: Create `research-os/control-rights/control-point-scorecard.md`**

Write:

```md
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
- 用 `metrics/` 和 `hypotheses/` 校验评分。
- 对低置信度候选补充证据和反证。
```

- [ ] **Step 5: Create `research-os/control-rights/candidates.md`**

Write:

```md
# 控制点候选

## 结论

本文件记录未来 10 年电力产业控制权候选。候选不是股票推荐，而是需要继续研究的控制点和资产类型。

## Candidate: dispatch-layer

```yaml
candidate:
  layer: dispatch
  asset_type: market and system balancing capability
  control_point: Dispatch layer controls real-time complexity across generation, storage, load, and market rules.
score:
  complexity_control: 5
  bottleneck_power: 4
  pricing_power: 3
  data_advantage: 4
  organizational_dependency: 3
  supply_response_lag: 4
  durability: 4
evidence:
  - Renewable penetration increases balancing complexity.
  - Power market reform may price reliability and flexibility.
counter_evidence:
  - Regulators or grid operators may capture most value.
  - Market reform may progress slowly.
confidence: medium
next_action: Track dispatch market reform and link to metrics/metric-catalog.md.
```

## Candidate: EMS

```yaml
candidate:
  layer: EMS
  asset_type: enterprise energy management operating layer
  control_point: EMS may become the operating layer for distributed generation, storage, charging, and flexible load.
score:
  complexity_control: 4
  bottleneck_power: 3
  pricing_power: 3
  data_advantage: 4
  organizational_dependency: 5
  supply_response_lag: 3
  durability: 4
evidence:
  - Customers need energy cost, reliability, and compliance management.
  - Workflow integration can raise switching costs.
counter_evidence:
  - EMS may commoditize if switching costs stay low.
  - Utilities or grid operators may control dispatch instead.
confidence: medium
next_action: Search for customer dependency and data feedback evidence.
```
```

- [ ] **Step 6: Verify control-rights module**

Run:

```bash
find research-os/control-rights -type f -print
rg -n "complexity_control|bottleneck_power|pricing_power|data_advantage|organizational_dependency|supply_response_lag|durability|股票推荐|dispatch-layer|EMS" research-os/control-rights
```

Expected: four control-rights files exist, and scorecard fields are found.

- [ ] **Step 7: Commit control-rights module**

Run:

```bash
git add research-os/control-rights
git commit -m "docs: add power control rights analysis module"
```

Expected: commit succeeds.

## Task 6: Wire Agents and Root Instructions

**Files:**
- Modify: `research-os/AGENTS.md`
- Modify: `research-os/agents/README.md`
- Modify: `research-os/agents/industry-observer.md`
- Modify: `research-os/agents/hypothesis-tracker.md`
- Modify: `research-os/agents/control-point-finder.md`

- [ ] **Step 1: Update `research-os/AGENTS.md` directory responsibilities**

Replace the `## 目录职责` list with:

```md
## 目录职责

- `beliefs/`：长期投资原则和底层信念。
- `frameworks/`：可复用分析框架和评分方法。
- `industries/`：行业级研究资产。
- `data/`：数据采集层，记录能源行业事实和 weekly signal。
- `metrics/`：指标计算层，把事实转成可比较指标和指标判断。
- `observations/`：原始事实、数据、新闻、财报、政策和调研记录。
- `insights/`：由事实和指标提炼出的可验证判断，使用洞察卡片格式记录假设、证据、反证、置信度和下一步动作。
- `hypotheses/`：假设跟踪系统，维护核心判断、状态、证据、反证和置信度变化。
- `control-rights/`：控制权分析模块，识别未来 10 年电力产业控制点候选，不输出股票推荐或交易动作。
- `decisions/`：买入、卖出、观望、仓位调整和复盘记录；Energy Research OS v0.1 暂不使用本目录输出交易动作。
- `agents/`：AI 或研究助手执行任务时使用的工作指令，具体角色和输出规范见 `agents/README.md`。
```

- [ ] **Step 2: Update `research-os/agents/README.md` flow**

Replace the `## Agent 流程` section with:

```md
## Agent 流程

```text
Industry Observer -> data/ -> metrics/ -> insights/ -> hypotheses/ -> control-rights/
```

Agent 不直接输出股票推荐、交易动作或仓位建议。
```

Add this section after `## 输出关系`:

```md
## 输出落点

- `Industry Observer` 的 weekly signal 写入 `data/collection-log.md`。
- `Hypothesis Tracker` 的状态更新写入 `hypotheses/hypothesis-ledger.md`。
- `Control Point Finder` 的候选控制点写入 `control-rights/candidates.md`。
- 能改变判断的输出应同步形成 `insights/` 洞察卡片。
```

- [ ] **Step 3: Update `research-os/agents/industry-observer.md`**

Add this section before `## 禁止事项`:

```md
## 输出落点

- weekly signal 写入 `data/collection-log.md`。
- 可比较指标写入或更新 `metrics/calculation-log.md`。
- 改变判断的信号写入 `insights/`。
- 验证或削弱假设的信号写入 `hypotheses/hypothesis-ledger.md`。
```

- [ ] **Step 4: Update `research-os/agents/hypothesis-tracker.md`**

Add this section before `## 禁止事项`:

```md
## 输出落点

- 假设状态写入 `hypotheses/hypothesis-ledger.md`。
- 电力控制权相关假设写入 `hypotheses/energy/power-control-rights.md`。
- 被验证、削弱或推翻的重要假设，应更新对应 `insights/` 洞察卡片。
```

- [ ] **Step 5: Update `research-os/agents/control-point-finder.md`**

Add this section before `## 禁止事项`:

```md
## 输出落点

- 控制点候选写入 `control-rights/candidates.md`。
- 控制点评分写入 `control-rights/control-point-scorecard.md`。
- 层级判断写入 `control-rights/power-layer-map.md`。
- 支撑或反证控制点的指标，应链接回 `metrics/`。
```

- [ ] **Step 6: Verify wiring**

Run:

```bash
rg -n "data/collection-log.md|metrics/calculation-log.md|hypotheses/hypothesis-ledger.md|control-rights/candidates.md|暂不使用本目录输出交易动作|不输出股票推荐或交易动作" research-os/AGENTS.md research-os/agents
```

Expected: all output destinations and prohibition lines are found.

- [ ] **Step 7: Commit wiring updates**

Run:

```bash
git add research-os/AGENTS.md research-os/agents
git commit -m "docs: wire energy research agents to v0.1 modules"
```

Expected: commit succeeds.

## Task 7: Final Verification and Push

**Files:**
- Verify all files under `research-os/`

- [ ] **Step 1: Verify expected files exist**

Run:

```bash
find research-os -type f -print
```

Expected: output includes all new v0.1 files:

```text
research-os/data/README.md
research-os/data/sources.md
research-os/data/collection-log.md
research-os/data/schemas/weekly-signal.md
research-os/metrics/README.md
research-os/metrics/metric-catalog.md
research-os/metrics/power-layer-metrics.md
research-os/metrics/calculation-log.md
research-os/insights/examples/stable-capacity-becomes-scarce.md
research-os/hypotheses/README.md
research-os/hypotheses/hypothesis-ledger.md
research-os/hypotheses/energy/power-control-rights.md
research-os/control-rights/README.md
research-os/control-rights/power-layer-map.md
research-os/control-rights/control-point-scorecard.md
research-os/control-rights/candidates.md
```

- [ ] **Step 2: Verify v0.1 requirements**

Run:

```bash
rg -n "数据采集层|指标计算层|洞察卡片|假设跟踪系统|控制权分析模块|未来 10 年电力产业控制权|不输出股票推荐|不输出交易|不开发交易功能|不开发股票推荐功能" research-os docs/superpowers/specs/2026-06-05-energy-research-os-v0.1-design.md
```

Expected: all v0.1 modules, target, and prohibitions are found.

- [ ] **Step 3: Verify no placeholders**

Run:

```bash
rg -n "T[D]BD|T[O]DO|待[定]|占[位]|FIXM[E]|x[x]x|X[X]X" research-os docs/superpowers
```

Expected: no matches.

- [ ] **Step 4: Verify Git state**

Run:

```bash
git status --short --branch
git log --oneline --decorate -8
```

Expected: working tree is clean and local `main` has the new v0.1 commits.

- [ ] **Step 5: Push to origin**

Run:

```bash
GIT_SSH_COMMAND='ssh -i /Users/woohuaca/.ssh/id_ed25519_github_woohuaca -o IdentitiesOnly=yes -o StrictHostKeyChecking=accept-new -p 443' git push origin main
```

Expected: push succeeds.

- [ ] **Step 6: Verify remote main**

Run:

```bash
GIT_SSH_COMMAND='ssh -i /Users/woohuaca/.ssh/id_ed25519_github_woohuaca -o IdentitiesOnly=yes -o StrictHostKeyChecking=accept-new -p 443' git ls-remote --heads origin main
```

Expected: remote `refs/heads/main` points to the latest local commit.
