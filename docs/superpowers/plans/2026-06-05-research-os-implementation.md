# Research OS Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create the first version of `research-os/` as a Markdown-based investment research operating system for secondary-market stock decisions.

**Architecture:** The structure is decision-centered. `beliefs/` defines stable investment principles, `frameworks/` turns them into reusable analysis methods, `industries/energy/` provides the first industry sample, `observations/` captures facts, `insights/` captures judgments, and `decisions/` turns research into investment actions.

**Tech Stack:** Markdown files and shell verification commands. No application runtime, database, package manager, or generated build artifacts are required.

---

## File Structure

Create these directories and files under `/Users/woohuaca/Documents/invest-kkk/research-os`:

```text
research-os/
├── AGENTS.md
├── beliefs/
│   ├── investment-principles.md
│   ├── control-rights-theory.md
│   └── bottleneck-theory.md
├── frameworks/
│   ├── industry-analysis.md
│   ├── energy-framework.md
│   └── company-score-model.md
├── industries/
│   └── energy/
│       ├── value-chain.md
│       ├── players.md
│       ├── indicators.md
│       └── hypotheses.md
├── insights/
├── decisions/
├── observations/
└── agents/
```

The current workspace is not a Git repository, so implementation must verify files directly instead of committing.

### Task 1: Create Directory Skeleton

**Files:**
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/beliefs/`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/frameworks/`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/industries/energy/`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/insights/`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/decisions/`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/observations/`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/agents/`

- [ ] **Step 1: Create directories**

Run:

```bash
mkdir -p research-os/beliefs research-os/frameworks research-os/industries/energy research-os/insights research-os/decisions research-os/observations research-os/agents
```

Expected: command exits with status `0`.

- [ ] **Step 2: Verify directories exist**

Run:

```bash
find research-os -type d -print
```

Expected output includes exactly these directories:

```text
research-os
research-os/agents
research-os/beliefs
research-os/decisions
research-os/frameworks
research-os/industries
research-os/industries/energy
research-os/insights
research-os/observations
```

### Task 2: Create Root Research Instructions

**Files:**
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/AGENTS.md`

- [ ] **Step 1: Write root instructions**

Create `/Users/woohuaca/Documents/invest-kkk/research-os/AGENTS.md` with this content:

```md
# Research OS 工作指令

## 目标

本目录是长期投资研究操作系统，服务二级市场股票投资决策。

所有研究都应最终帮助判断：

1. 一家公司是否值得长期拥有。
2. 当前行业和周期位置是否支持买入。
3. 估值是否提供足够安全边际。
4. 应该买入、卖出、观望，还是调整仓位。
5. 哪些事实会证明原判断错误。

## 工作原则

- 默认使用中文。
- Markdown 文件是研究事实、判断和决策的源文件。
- 先写结论，再写逻辑，最后写细节。
- 区分事实、解释、假设、判断和投资动作。
- 所有判断都要写出反证条件。
- 不把资料收集当成研究成果。
- 不为了显得完整而加入不能影响决策的内容。

## 信息流

```text
投资信念 -> 分析框架 -> 行业研究 -> 公司评分 -> 投资决策 -> 持续观察 -> 修正假设
```

## 目录职责

- `beliefs/`：长期投资原则和底层信念。
- `frameworks/`：可复用分析框架和评分方法。
- `industries/`：行业级研究资产。
- `observations/`：原始事实、数据、新闻、财报、政策和调研记录。
- `insights/`：由事实提炼出的可验证判断。
- `decisions/`：买入、卖出、观望、仓位调整和复盘记录。
- `agents/`：AI 或研究助手执行任务时使用的工作指令。
```

- [ ] **Step 2: Verify root instructions**

Run:

```bash
sed -n '1,220p' research-os/AGENTS.md
```

Expected: output contains `本目录是长期投资研究操作系统` and `投资信念 -> 分析框架 -> 行业研究 -> 公司评分 -> 投资决策 -> 持续观察 -> 修正假设`.

### Task 3: Create Beliefs Templates

**Files:**
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/beliefs/investment-principles.md`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/beliefs/control-rights-theory.md`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/beliefs/bottleneck-theory.md`

- [ ] **Step 1: Write `investment-principles.md`**

Create `/Users/woohuaca/Documents/invest-kkk/research-os/beliefs/investment-principles.md` with this content:

```md
# 投资原则

## 结论

长期投资只值得投入到能持续创造自由现金流、能抵抗竞争侵蚀、且价格低于长期价值的公司。

## 为什么重要

投资原则用于约束后续行业研究、公司评分和投资决策，避免被短期叙事、价格波动或单一指标牵引。

## 判断框架

### 值得长期拥有的公司

- 长期需求真实存在，不依赖一次性补贴或短期主题。
- 公司拥有成本、品牌、网络、资源、牌照、渠道或组织能力形成的防御力。
- 资本回报率长期高于资本成本。
- 自由现金流可解释、可持续，并能回到股东或再投入高回报机会。
- 管理层资本配置理性，少做摧毁价值的扩张。

### 不值得追逐的收益

- 只依赖估值扩张而没有基本面改善。
- 只依赖周期价格短期上行而缺少退出纪律。
- 需要过多不可验证假设才能成立。
- 风险暴露无法通过仓位、估值或跟踪指标控制。

## 当前判断

- 强判断：投资收益应主要来自企业长期价值增长和价格低于价值时的再定价。
- 弱判断：周期行业也可以长期投资，但必须明确周期位置、资本开支纪律和退出条件。
- 未知项：不同市场环境下，估值安全边际应如何量化。

## 反证条件

如果长期持有收益主要来自估值变化而非企业价值增长，或者公司基本面判断经常被短期变量推翻，本原则需要修正。

## 下一步观察

- 复盘历史投资中收益来源：盈利增长、分红、估值变化、汇率或周期。
- 比较不同类型公司的资本回报率和自由现金流质量。
- 记录每次买入时的核心假设和后续反证情况。
```

- [ ] **Step 2: Write `control-rights-theory.md`**

Create `/Users/woohuaca/Documents/invest-kkk/research-os/beliefs/control-rights-theory.md` with this content:

```md
# 控制权理论

## 结论

利润长期流向掌握关键控制权的一方。研究公司时，必须先判断它控制的是资源、渠道、客户关系、技术标准、产能、数据、牌照，还是仅承担可替代执行环节。

## 为什么重要

控制权决定议价能力、利润分配、抗周期能力和估值上限。没有控制权的公司，即使短期利润好，也可能在竞争或周期反转中被重新定价。

## 判断框架

### 控制权来源

- 资源控制：稀缺资源、低成本资产、地理位置、矿权或长期合同。
- 客户控制：高切换成本、强渠道、稳定复购、关键客户关系。
- 技术控制：专利、标准、工艺、数据、系统集成能力。
- 资本控制：低成本融资、逆周期扩张能力、资产负债表韧性。
- 规则控制：牌照、监管准入、政策地位或行业标准制定权。

### 判断问题

- 如果行业利润池扩大，谁最先受益？
- 如果行业利润池收缩，谁最能保住现金流？
- 如果上下游重新谈判，谁能改变价格和条款？
- 如果新进入者出现，哪一环节最难被复制？

## 当前判断

- 强判断：控制权比短期利润率更重要。
- 弱判断：控制权可能随技术、政策和资本周期迁移。
- 未知项：不同控制权之间如何排序，仍需要通过行业和公司案例校准。

## 反证条件

如果一家没有明显控制权的公司能长期维持高资本回报率，或掌握控制权的一方无法获得超额收益，本理论需要修正。

## 下一步观察

- 在能源行业价值链中标出不同环节的控制权来源。
- 比较资源型、设备型、运营型和销售型公司的利润稳定性。
- 记录周期反转时利润在产业链内如何重新分配。
```

- [ ] **Step 3: Write `bottleneck-theory.md`**

Create `/Users/woohuaca/Documents/invest-kkk/research-os/beliefs/bottleneck-theory.md` with this content:

```md
# 瓶颈理论

## 结论

超额收益通常来自行业瓶颈。判断一家公司的投资价值，必须识别行业真正受限的是需求、资源、产能、技术、渠道、资本、监管，还是组织执行。

## 为什么重要

瓶颈决定利润池的位置。研究如果只看需求增长，而不看瓶颈在哪里，容易买到增长中的低回报环节。

## 判断框架

### 常见瓶颈

- 需求瓶颈：终端需求不足或替代品增强。
- 资源瓶颈：低成本资源、土地、矿权、能源输入或原料稀缺。
- 产能瓶颈：建设周期长、扩产受限、设备交付慢。
- 技术瓶颈：良率、效率、专利、工艺或系统能力难以复制。
- 渠道瓶颈：触达客户、履约网络、品牌信任或服务能力稀缺。
- 资本瓶颈：融资成本、资产负债表、现金流承受力。
- 监管瓶颈：牌照、审批、环保、并网、价格机制或安全要求。

### 判断问题

- 行业增长时，最先短缺的是什么？
- 行业下行时，最先出清的是什么？
- 瓶颈能否被资本快速复制？
- 公司是否拥有瓶颈，还是只是受瓶颈影响？

## 当前判断

- 强判断：瓶颈位置比行业增速更能解释超额收益。
- 弱判断：瓶颈会随周期阶段迁移。
- 未知项：如何量化瓶颈持续时间和可复制难度，需要行业指标支持。

## 反证条件

如果行业利润长期流向非瓶颈环节，或者瓶颈环节无法获得更高资本回报率，本理论需要修正。

## 下一步观察

- 在能源行业中识别资源、产能、并网、储能、资本和监管瓶颈。
- 跟踪瓶颈变化与公司毛利率、资本回报率、现金流之间的关系。
- 记录每个投资决策中假设的瓶颈位置，并在复盘中验证。
```

- [ ] **Step 4: Verify beliefs files**

Run:

```bash
find research-os/beliefs -type f -print
rg -n "## 结论|## 反证条件|## 下一步观察" research-os/beliefs
```

Expected: three files exist, and each file contains `## 结论`, `## 反证条件`, and `## 下一步观察`.

### Task 4: Create Framework Templates

**Files:**
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/frameworks/industry-analysis.md`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/frameworks/energy-framework.md`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/frameworks/company-score-model.md`

- [ ] **Step 1: Write `industry-analysis.md`**

Create `/Users/woohuaca/Documents/invest-kkk/research-os/frameworks/industry-analysis.md` with this content:

```md
# 行业分析框架

## 结论

行业分析的目的不是描述行业，而是判断行业是否存在可投资的长期利润池，以及哪些公司最可能获得这部分利润。

## 为什么重要

公司投资决策必须放在行业结构中判断。好公司如果处在差行业，可能回报有限；普通公司如果掌握阶段性瓶颈，也可能有中期机会。

## 判断框架

### 1. 需求

- 需求来自真实经济活动、替代升级、政策驱动，还是金融条件。
- 需求增长的持续时间、弹性和可预测性。
- 需求是否对价格、利率、补贴或宏观周期高度敏感。

### 2. 供给

- 产能建设周期和退出难度。
- 新进入者门槛。
- 行业是否容易过度资本开支。
- 供给纪律由市场、监管、资源还是头部公司决定。

### 3. 利润池

- 利润主要在哪些环节产生。
- 利润池是否稳定，还是在周期中剧烈迁移。
- 谁承担风险，谁获得收益。

### 4. 竞争格局

- 集中度、份额变化和价格纪律。
- 差异化来源。
- 规模优势是否真实存在。

### 5. 关键变量

- 价格、销量、成本、库存、资本开支、政策、技术变化和资产负债表。

## 当前判断

- 强判断：行业研究必须落到利润池、瓶颈和公司胜率。
- 弱判断：不同行业的指标权重应不同，不能套用同一评分。
- 未知项：行业周期位置与公司估值安全边际之间的映射方式需要继续校准。

## 反证条件

如果行业分析不能提高公司评分、仓位判断或风险识别质量，该框架需要删减或重写。

## 下一步观察

- 将能源行业作为第一个样板，验证本框架是否能解释利润池和周期。
- 记录每次公司决策中真正起作用的行业变量。
- 删除不能改变投资判断的行业描述项。
```

- [ ] **Step 2: Write `energy-framework.md`**

Create `/Users/woohuaca/Documents/invest-kkk/research-os/frameworks/energy-framework.md` with this content:

```md
# 能源行业分析框架

## 结论

能源行业研究必须同时处理长期需求、供给约束、资本开支周期、政策规则和价格波动。只看需求增长或只看价格趋势，都不足以形成投资决策。

## 为什么重要

能源行业的利润往往在周期中剧烈迁移。投资决策需要判断公司是长期价值拥有者、周期交易标的，还是应避免的高波动资产。

## 判断框架

### 1. 能源类型

- 化石能源：油、气、煤。
- 电力资产：火电、水电、核电、风电、光伏。
- 能源基础设施：管网、电网、储能、充电、运输。
- 能源设备与服务：设备制造、工程服务、数字化和运维。

### 2. 价值链位置

- 上游资源。
- 中游运输、储存和转化。
- 下游销售、发电、用能服务。
- 设备和技术服务。

### 3. 周期变量

- 供需缺口。
- 库存水平。
- 资本开支。
- 产能投放和退出。
- 价格机制。
- 政策和监管变化。

### 4. 公司质量

- 低成本资源或资产。
- 现金流稳定性。
- 资产负债表韧性。
- 资本开支纪律。
- 分红和回购能力。

## 当前判断

- 强判断：能源投资必须区分长期资产价值和周期价格收益。
- 弱判断：高分红资产可能适合长期持有，但仍需警惕政策和资本开支周期。
- 未知项：不同能源子行业的估值锚需要分别建立。

## 反证条件

如果能源行业中的公司回报主要由公司能力而非资源、周期和政策解释，本框架需要降低行业变量权重。

## 下一步观察

- 建立能源价值链图谱。
- 梳理不同环节的代表公司和利润来源。
- 确定油价、电价、库存、资本开支、负债率和分红率等核心指标。
```

- [ ] **Step 3: Write `company-score-model.md`**

Create `/Users/woohuaca/Documents/invest-kkk/research-os/frameworks/company-score-model.md` with this content:

```md
# 公司评分模型

## 结论

公司评分模型用于把研究判断转化为投资动作。评分不是为了精确计算，而是为了强迫比较长期质量、周期位置、估值、风险和反证条件。

## 为什么重要

没有评分模型，研究容易停留在叙事层。评分模型让不同公司、不同时间和不同仓位决策可以被比较和复盘。

## 判断框架

总分 100 分，默认维度如下：

| 维度 | 权重 | 判断问题 |
| --- | ---: | --- |
| 行业结构 | 20 | 行业是否有长期利润池，公司所在环节是否有吸引力？ |
| 公司质量 | 25 | 公司是否有控制权、瓶颈、资本回报和现金流韧性？ |
| 周期位置 | 15 | 当前供需、价格、库存和资本开支是否支持买入？ |
| 估值与安全边际 | 20 | 当前价格是否低于保守估计的长期价值？ |
| 管理层与资本配置 | 10 | 管理层是否理性分配资本、尊重股东回报？ |
| 风险与反证清晰度 | 10 | 主要风险是否可识别、可跟踪、可控制？ |

### 决策映射

| 分数 | 默认动作 | 说明 |
| ---: | --- | --- |
| 85-100 | 重点研究或买入候选 | 仍需估值和风险确认。 |
| 70-84 | 观察或小仓位 | 需要明确缺口和触发条件。 |
| 55-69 | 仅跟踪 | 暂不形成买入决策。 |
| 55 以下 | 回避 | 除非出现重大事实变化。 |

## 当前判断

- 强判断：评分必须服务投资动作，而不是替代判断。
- 弱判断：能源行业需要提高周期位置和资本开支纪律的权重。
- 未知项：分数与仓位比例之间的关系需要通过复盘校准。

## 反证条件

如果高分公司投资结果持续差于低分公司，或评分无法提前暴露主要风险，本模型需要调整权重。

## 下一步观察

- 用能源行业代表公司试评分。
- 记录每次评分和后续投资结果。
- 复盘哪些维度真正解释收益和亏损。
```

- [ ] **Step 4: Verify framework files**

Run:

```bash
find research-os/frameworks -type f -print
rg -n "## 结论|## 判断框架|## 反证条件" research-os/frameworks
```

Expected: three files exist, and each file contains `## 结论`, `## 判断框架`, and `## 反证条件`.

### Task 5: Create Energy Industry Templates

**Files:**
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/industries/energy/value-chain.md`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/industries/energy/players.md`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/industries/energy/indicators.md`
- Create: `/Users/woohuaca/Documents/invest-kkk/research-os/industries/energy/hypotheses.md`

- [ ] **Step 1: Write `value-chain.md`**

Create `/Users/woohuaca/Documents/invest-kkk/research-os/industries/energy/value-chain.md` with this content:

```md
# 能源价值链

## 结论

能源行业的投资价值取决于价值链中谁掌握资源、基础设施、价格机制、客户关系和资本开支纪律。不能只按上游、中游、下游做静态分类。

## 为什么重要

价值链分析用于判断利润池位置、周期风险承担者和公司控制权来源，是公司评分和仓位判断的基础。

## 判断框架

### 上游

- 资源获取、勘探开发、开采和初级处理。
- 关键变量：资源成本、储量质量、开采成本、税费、资本开支。

### 中游

- 运输、储存、管网、电网、交易和转化。
- 关键变量：利用率、准入规则、价格机制、资产寿命、监管回报。

### 下游

- 发电、销售、终端服务和用能管理。
- 关键变量：客户黏性、价格传导、需求波动、政策约束。

### 设备与服务

- 设备制造、工程建设、运维和数字化。
- 关键变量：技术迭代、订单周期、毛利率、客户集中度。

## 当前判断

- 强判断：低成本资源和关键基础设施更可能形成长期控制权。
- 弱判断：设备与服务环节可能在技术变化期获得阶段性瓶颈收益。
- 未知项：不同能源子行业的利润池迁移速度不同，需要分开验证。

## 反证条件

如果利润长期稳定流向不掌握资源、基础设施或客户关系的环节，本价值链判断需要修正。

## 下一步观察

- 标出每个环节的代表公司。
- 跟踪不同环节的毛利率、资本回报率和自由现金流。
- 记录价格上行和下行时利润如何在价值链中迁移。
```

- [ ] **Step 2: Write `players.md`**

Create `/Users/woohuaca/Documents/invest-kkk/research-os/industries/energy/players.md` with this content:

```md
# 能源行业玩家

## 结论

能源行业玩家应按价值链位置、控制权来源、周期暴露和资本开支纪律分类，而不是只按主营业务名称分类。

## 为什么重要

玩家分类用于寻找可比公司、识别竞争格局和判断公司评分的相对位置。

## 判断框架

| 玩家类型 | 控制权来源 | 主要风险 | 需要观察 |
| --- | --- | --- | --- |
| 资源型公司 | 低成本资源、储量、牌照 | 商品价格、税费、资本开支 | 储量、成本、产量、分红 |
| 基础设施公司 | 管网、电网、储运资产 | 监管回报、利用率 | 准许收益、利用率、负债 |
| 发电运营商 | 装机、并网、运营效率 | 电价、燃料成本、政策 | 电价、小时数、燃料价差 |
| 设备制造商 | 技术、成本、客户认证 | 产能过剩、价格竞争 | 订单、毛利率、产能 |
| 能源服务商 | 工程能力、客户关系 | 项目周期、应收账款 | 订单、回款、现金流 |

## 当前判断

- 强判断：同一能源主题下，不同玩家的风险收益结构差异很大。
- 弱判断：资源型和基础设施型公司更适合长期基本面研究，设备型公司更需要周期跟踪。
- 未知项：不同市场中监管机制对基础设施资产估值的影响需要单独研究。

## 反证条件

如果不同玩家类型在周期中的表现高度同质化，本分类方式需要简化。

## 下一步观察

- 为每类玩家补充代表公司。
- 建立同类公司比较表。
- 记录不同玩家在能源价格、利率和政策变化下的表现。
```

- [ ] **Step 3: Write `indicators.md`**

Create `/Users/woohuaca/Documents/invest-kkk/research-os/industries/energy/indicators.md` with this content:

```md
# 能源行业指标

## 结论

能源行业指标必须同时覆盖价格、供需、库存、资本开支、政策、资产负债表和股东回报。单一价格指标不能支撑投资决策。

## 为什么重要

指标用于判断周期位置、验证行业假设、触发决策复盘，并避免只凭叙事调整仓位。

## 判断框架

### 价格指标

- 油价、气价、煤价、电价。
- 价差、长协价、现货价和期货曲线。

### 供需指标

- 产量、消费量、进口、出口、开工率。
- 新增产能、退出产能、项目延期。

### 库存指标

- 商业库存、战略库存、渠道库存。
- 库存天数和库存变化速度。

### 资本开支指标

- 行业资本开支。
- 公司资本开支。
- 项目回报率和建设周期。

### 政策指标

- 价格机制。
- 补贴、税费、环保、安全、并网和容量规则。

### 公司指标

- 单位成本、毛利率、资本回报率、自由现金流、负债率、分红率。

## 当前判断

- 强判断：能源投资需要用指标跟踪假设，而不是用指标堆砌信息。
- 弱判断：不同子行业应有不同核心指标组合。
- 未知项：哪些指标具有领先性，哪些只是同步或滞后指标，需要通过复盘确认。

## 反证条件

如果指标变化无法解释行业利润、公司现金流或股价重估，需要重新筛选指标。

## 下一步观察

- 为每个能源子行业确定 5-8 个核心指标。
- 为每个投资决策指定复盘触发指标。
- 记录指标变化和投资结论变化之间的关系。
```

- [ ] **Step 4: Write `hypotheses.md`**

Create `/Users/woohuaca/Documents/invest-kkk/research-os/industries/energy/hypotheses.md` with this content:

```md
# 能源行业假设

## 结论

能源行业研究必须显式写出可证伪假设。没有反证条件的行业判断，不能进入投资决策。

## 为什么重要

能源行业受周期、政策、资本开支和技术变化共同影响。假设管理可以减少确认偏误，并让复盘有依据。

## 判断框架

每条假设使用以下结构：

```md
## 假设：一句话描述

### 当前结论

说明当前判断。

### 支撑事实

列出已经观察到的事实。

### 投资影响

说明它影响哪些公司、估值、仓位或风险判断。

### 反证条件

说明哪些事实出现后，该假设需要下调或推翻。

### 下一步观察

列出需要跟踪的指标、事件或文件。
```

## 当前判断

- 强判断：能源行业假设必须区分长期结构性假设和中期周期假设。
- 弱判断：周期假设的有效期通常短于公司质量判断。
- 未知项：哪些假设最能解释长期收益，需要通过决策复盘沉淀。

## 反证条件

如果假设列表不能影响公司评分、仓位或风险判断，就说明假设写得过泛，需要重写。

## 下一步观察

- 建立第一批能源行业长期假设。
- 建立第一批能源行业周期假设。
- 将每个投资决策链接到相关假设。
```

- [ ] **Step 5: Verify energy industry files**

Run:

```bash
find research-os/industries/energy -type f -print
rg -n "## 结论|## 判断框架|## 反证条件|## 下一步观察" research-os/industries/energy
```

Expected: four files exist, and each file contains `## 结论`, `## 判断框架`, `## 反证条件`, and `## 下一步观察`.

### Task 6: Create Empty Operational Directories

**Files:**
- Directory only: `/Users/woohuaca/Documents/invest-kkk/research-os/insights/`
- Directory only: `/Users/woohuaca/Documents/invest-kkk/research-os/decisions/`
- Directory only: `/Users/woohuaca/Documents/invest-kkk/research-os/observations/`
- Directory only: `/Users/woohuaca/Documents/invest-kkk/research-os/agents/`

- [ ] **Step 1: Confirm operational directories are intentionally empty**

Run:

```bash
find research-os/insights research-os/decisions research-os/observations research-os/agents -maxdepth 1 -type f -print
```

Expected: no file paths are printed.

- [ ] **Step 2: Verify root instructions define their future purpose**

Run:

```bash
rg -n '`insights/`|`decisions/`|`observations/`|`agents/`' research-os/AGENTS.md
```

Expected: output contains one responsibility line for each operational directory.

### Task 7: Final Verification

**Files:**
- Verify: `/Users/woohuaca/Documents/invest-kkk/research-os/`

- [ ] **Step 1: Verify all expected Markdown files exist**

Run:

```bash
find research-os -type f -print
```

Expected output includes exactly these files:

```text
research-os/AGENTS.md
research-os/beliefs/bottleneck-theory.md
research-os/beliefs/control-rights-theory.md
research-os/beliefs/investment-principles.md
research-os/frameworks/company-score-model.md
research-os/frameworks/energy-framework.md
research-os/frameworks/industry-analysis.md
research-os/industries/energy/hypotheses.md
research-os/industries/energy/indicators.md
research-os/industries/energy/players.md
research-os/industries/energy/value-chain.md
```

- [ ] **Step 2: Verify no implementation placeholders exist**

Run:

```bash
rg -n "T[D]BD|T[O]DO|待[定]|占[位]|FIXM[E]|x[x]x|X[X]X" research-os
```

Expected: no matches.

- [ ] **Step 3: Verify every template supports decision quality**

Run:

```bash
rg -n "## 结论|## 为什么重要|## 反证条件|## 下一步观察" research-os
```

Expected: every Markdown template except `research-os/AGENTS.md` contains the decision-oriented sections `## 结论`, `## 为什么重要`, `## 反证条件`, and `## 下一步观察`.

- [ ] **Step 4: Check Git availability**

Run:

```bash
git status --short
```

Expected in current workspace: `fatal: not a git repository (or any of the parent directories): .git`.

If the workspace is later initialized as a Git repository, replace this step with:

```bash
git add research-os docs/superpowers/specs/2026-06-05-research-os-design.md docs/superpowers/plans/2026-06-05-research-os-implementation.md
git commit -m "docs: add research os scaffold"
```
