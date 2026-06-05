# Energy Research OS v0.1 设计规格

## 结论

Energy Research OS v0.1 的目标是建立一套纯 Markdown 的能源研究操作系统，用于识别未来 10 年电力产业控制权资产。

v0.1 暂不开发交易功能，暂不开发股票推荐功能。它只建立研究链条、结构化输出和判断复盘机制。

核心数据流：

```text
数据采集 -> 指标计算 -> 洞察卡片 -> 假设跟踪 -> 控制权分析
```

每一层都必须服务同一个问题：

> 哪个电力产业层级正在获得复杂性控制权、瓶颈、定价权、数据优势或组织依赖？

## 背景

当前仓库已经具备 Research OS 雏形：

- `beliefs/`：投资原则、瓶颈理论、控制权理论。
- `frameworks/`：行业分析、能源框架、公司评分模型。
- `industries/energy/`：能源价值链、玩家、指标和假设骨架。
- `insights/`：洞察卡片格式。
- `agents/`：Industry Observer、Hypothesis Tracker、Control Point Finder。

当前缺口是：数据采集层、指标计算层、假设台账、控制权分析模块还没有独立结构。v0.1 要补齐这些模块，并把现有 agent 连接到可执行的研究流程中。

## 非目标

v0.1 不做以下事项：

1. 不开发交易功能。
2. 不开发股票推荐功能。
3. 不做自动爬虫或实时数据抓取。
4. 不建立数据库。
5. 不开发 Web UI。
6. 不对具体公司给出买入、卖出或仓位建议。

v0.1 只建立手动可执行、可复盘、后续可脚本化的 Markdown 研究系统。

## 架构

v0.1 采用“流水线 + 控制权资产”的混合架构：

1. 用流水线保证研究每周可以执行。
2. 用控制权资产目标约束所有输出，避免泛泛收集能源信息。
3. 保留现有 agents 作为执行者，而不是让 agent 成为目录结构本身。

目标结构：

```text
research-os/
├── data/
│   ├── README.md
│   ├── sources.md
│   ├── collection-log.md
│   └── schemas/
│       └── weekly-signal.md
├── metrics/
│   ├── README.md
│   ├── metric-catalog.md
│   ├── power-layer-metrics.md
│   └── calculation-log.md
├── insights/
│   ├── README.md
│   └── examples/
│       └── stable-capacity-becomes-scarce.md
├── hypotheses/
│   ├── README.md
│   ├── hypothesis-ledger.md
│   └── energy/
│       └── power-control-rights.md
└── control-rights/
    ├── README.md
    ├── power-layer-map.md
    ├── control-point-scorecard.md
    └── candidates.md
```

## 模块设计

### 1. 数据采集层

新增目录：`research-os/data/`

职责：

- 定义能源研究数据源。
- 记录每周采集事实和信号。
- 不直接形成投资结论。
- 将信号输入 `metrics/`、`insights/` 或 `hypotheses/`。

重点数据源：

- 国家能源局。
- 国家电网。
- 电力市场改革文件。
- 储能政策、装机、利用率和商业模式。
- 数据中心负荷、能耗、并网和电力需求。

核心输出：weekly signal。

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

`layer` 使用电力产业层级：

```text
generation / transmission / distribution / dispatch / EMS / VPP / operations_knowledge
```

### 2. 指标计算层

新增目录：`research-os/metrics/`

职责：

- 将事实转成可比较指标。
- 定义指标含义、口径、解释方式和使用限制。
- 不追求复杂量化，先保证指标能支持控制权判断。

指标类型：

- 增长指标：需求增长、装机增长、负荷增长、数据中心用电增长。
- 供给响应指标：扩产周期、并网速度、设备交付周期、人才和系统能力供给。
- 瓶颈指标：利用率、弃风弃光、峰谷价差、容量紧缺、调度约束。
- 控制权指标：定价权、数据优势、客户切换成本、组织依赖。
- 政策指标：电力市场改革、容量市场、辅助服务、需求响应。

核心文件：

- `metric-catalog.md`：指标总表。
- `power-layer-metrics.md`：按电力层级组织指标。
- `calculation-log.md`：记录每次指标判断如何得出。

### 3. 洞察卡片系统

增强目录：`research-os/insights/`

职责：

- 把事实和指标转成可证伪判断。
- 每张卡片只表达一个洞察。
- 洞察不等于投资动作。

保留现有字段：

```yaml
title:
date:
industry:
scope:
status:
confidence:
hypothesis:
evidence:
counter_evidence:
leading_indicators:
decision_impact:
next_action:
```

新增示例：

- `examples/stable-capacity-becomes-scarce.md`

该示例用于展示“稳定容量变稀缺”如何从行业事实进入洞察卡片。

### 4. 假设跟踪系统

新增目录：`research-os/hypotheses/`

职责：

- 维护核心判断台账。
- 跟踪假设状态：`active / verified / weakened / invalidated / resolved`。
- 保留被推翻假设，服务复盘。

初始核心假设：

1. 稳定容量会随着新能源渗透率提升而变稀缺。
2. 调度层比单一发电资产更可能获得复杂性控制权。
3. EMS 和虚拟电厂的价值取决于组织依赖，而不只是聚合容量。
4. 数据中心负荷增长会改变电力系统瓶颈位置。
5. 电力市场改革会把隐性系统价值显性定价。

核心输出：hypothesis ledger。

```yaml
hypothesis:
  id:
  title:
  statement:
  scope:
status:
confidence:
supporting_evidence:
counter_evidence:
linked_insights:
linked_metrics:
next_action:
```

### 5. 控制权分析模块

新增目录：`research-os/control-rights/`

职责：

- 识别未来 10 年电力产业控制权资产。
- 先分析层级和能力，再分析公司。
- 输出控制点候选，而不是股票建议。

分析层级：

```text
发电 -> 输电 -> 配电 -> 调度 -> EMS -> 虚拟电厂 -> 运维知识
```

评分维度：

| 维度 | 含义 |
| --- | --- |
| `complexity_control` | 是否控制复杂性 |
| `bottleneck_power` | 是否成为瓶颈 |
| `pricing_power` | 是否获得定价权 |
| `data_advantage` | 是否沉淀数据优势 |
| `organizational_dependency` | 是否形成组织依赖 |
| `supply_response_lag` | 供给响应是否慢 |
| `durability` | 控制权是否能持续 10 年 |

核心输出：control point candidate。

```yaml
candidate:
  layer:
  asset_type:
  control_point:
score:
  complexity_control:
  bottleneck_power:
  pricing_power:
  data_advantage:
  organizational_dependency:
  supply_response_lag:
  durability:
evidence:
counter_evidence:
confidence:
next_action:
```

## Agent 关系

现有 agents 作为执行者保留：

- `Industry Observer` 主要服务 `data/`。
- `Hypothesis Tracker` 主要服务 `hypotheses/`。
- `Control Point Finder` 主要服务 `control-rights/`。

v0.1 需要更新 `agents/README.md`，让 agent 输出明确落到对应目录。

## 数据流

```text
1. Industry Observer 记录 weekly signal
2. weekly signal 进入 data/collection-log.md
3. 可量化或可比较的信号进入 metrics/
4. 能改变判断的信号进入 insights/
5. 洞察更新 hypotheses/
6. 假设和指标共同更新 control-rights/
7. control-rights 输出控制点候选和下一步研究动作
```

任何一层都不能直接输出股票推荐或交易动作。

## 成功标准

v0.1 完成后应能做到：

1. 每周从指定数据源记录能源行业信号。
2. 将信号映射到电力产业层级。
3. 将信号转成指标定义、指标判断或洞察卡片。
4. 用假设台账追踪哪些判断正在被验证、削弱或推翻。
5. 用控制权 scorecard 识别候选控制点。
6. 明确记录置信度、反证条件和下一步动作。
7. 明确禁止交易功能和股票推荐功能。

## 风险

### 风险 1：数据采集变成新闻摘抄

缓解方式：所有 weekly signal 必须写 `impact` 和 `next_action`，并映射到电力产业层级。

### 风险 2：指标层过度量化

缓解方式：v0.1 只定义指标口径和解释方式，不追求复杂模型。

### 风险 3：控制权分析先有结论再找证据

缓解方式：每个候选控制点必须包含 `evidence`、`counter_evidence` 和 `confidence`。

### 风险 4：研究系统越权成推荐系统

缓解方式：所有模块都明确禁止输出买入、卖出、仓位或交易动作。

## 实施边界

下一步实施只包括：

1. 创建 v0.1 所需 Markdown 目录和模板。
2. 更新现有 agent 文档，让输出落到新模块。
3. 新增一个洞察卡片示例。
4. 更新根 `AGENTS.md` 的目录职责。
5. 提交并推送到 `origin/main`。

下一步实施不包括：

1. 自动采集脚本。
2. 数据库。
3. Web UI。
4. 股票推荐。
5. 交易功能。
