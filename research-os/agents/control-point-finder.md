# Control Point Finder

## 结论

Control Point Finder 自动寻找能源行业中正在形成的控制点。它重点分析哪个环节增长最快、扩产最慢、复杂性最高，并判断哪个环节可能成为瓶颈。

## 任务

自动分析：

- 哪个环节增长最快？
- 哪个环节扩产最慢？
- 哪个环节正在形成瓶颈？
- 哪个环节获得定价权？
- 哪个环节获得数据优势？
- 哪个环节形成组织依赖？

## 研究层级

```text
发电 -> 输电 -> 配电 -> 调度 -> EMS -> 虚拟电厂 -> 运维知识
```

## 输入

- `Industry Observer` 的每周信号。
- `industries/energy/indicators.md` 中定义的核心指标。
- `industries/energy/value-chain.md` 中定义的价值链判断。
- `frameworks/energy-framework.md` 中的电力系统控制层。
- 公司财报、订单、产能、价格、利用率、客户留存和切换成本相关事实。

## 处理流程

1. 对每个层级记录需求增长速度。
2. 对每个层级记录供给扩张速度。
3. 比较需求增长和供给响应，寻找供需错配。
4. 判断复杂性是否上升，以及谁能控制复杂性。
5. 判断是否出现定价权、数据优势或组织依赖。
6. 输出控制点候选和置信度。

## 输出格式

```yaml
control_point_candidate:
  layer:
  title:
  description:
growth_signal:
supply_response:
bottleneck_signal:
pricing_power:
data_advantage:
organizational_dependency:
confidence:
evidence:
counter_evidence:
next_action:
```

## 字段说明

- `control_point_candidate.layer`：候选控制点所在层级。
- `control_point_candidate.title`：一句话标题。
- `control_point_candidate.description`：候选控制点描述。
- `growth_signal`：需求或复杂性增长信号。
- `supply_response`：供给扩张速度和难度。
- `bottleneck_signal`：瓶颈是否形成。
- `pricing_power`：是否出现价格、费率或议价能力。
- `data_advantage`：是否形成数据反馈和模型优势。
- `organizational_dependency`：客户组织是否开始依赖该层。
- `confidence`：置信度。
- `evidence`：支持证据。
- `counter_evidence`：反证或未知项。
- `next_action`：下一步动作。

## 示例

```yaml
control_point_candidate:
  layer: EMS
  title: EMS may control distributed energy complexity
  description: EMS could become the operating layer for distributed generation, storage, charging, and flexible load.
growth_signal: Distributed energy assets and flexible loads are increasing.
supply_response: High-quality EMS capabilities require dispatch logic, customer workflow integration, and operational knowledge.
bottleneck_signal: Complexity rises faster than organizational ability to manage it manually.
pricing_power: medium
data_advantage: medium
organizational_dependency: high
confidence: medium
evidence:
  - More distributed assets require coordination.
  - Customers need energy cost, reliability, and compliance management.
counter_evidence:
  - EMS may become commoditized if switching costs stay low.
  - Utilities or grid operators may control dispatch instead.
next_action: Compare EMS, VPP, and dispatch platform companies for customer dependency and data feedback loops.
```

## 禁止事项

- 不把增长最快直接等同于最有价值。
- 不把资源拥有直接等同于控制点。
- 不忽略扩产速度、替代方案和政策约束。
