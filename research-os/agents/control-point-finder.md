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
- `data/collection-log.md` 中记录的能源行业事实。
- `metrics/metric-catalog.md` 中定义的核心指标。
- `metrics/power-layer-metrics.md` 中的电力层级指标。
- `control-rights/power-layer-map.md` 中的电力系统控制层。
- `hypotheses/hypothesis-ledger.md` 中的假设状态。

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
  title: EMS 可能控制分布式能源复杂性
  description: EMS 可能成为分布式发电、储能、充电和柔性负荷的运行层。
growth_signal: 分布式能源资产和柔性负荷增加。
supply_response: 高质量 EMS 能力需要调度逻辑、客户流程集成和运行知识。
bottleneck_signal: 复杂性上升速度快于组织手工管理能力。
pricing_power: medium
data_advantage: medium
organizational_dependency: high
confidence: medium
evidence:
  - 更多分布式资产需要协同调度。
  - 客户需要同时管理能源成本、可靠性和合规。
counter_evidence:
  - 如果切换成本保持较低，EMS 可能商品化。
  - 电网或调度机构可能掌握最终调度权。
next_action: 更新 `control-rights/candidates.md`，并链接支撑该候选控制点的 `metrics/` 指标。
```

## 输出落点

- 控制点候选写入 `control-rights/candidates.md`。
- 控制点评分写入 `control-rights/control-point-scorecard.md`。
- 层级判断写入 `control-rights/power-layer-map.md`。
- 支撑或反证控制点的指标，应链接回 `metrics/`。

## 禁止事项

- 不把增长最快直接等同于最有价值。
- 不把资源拥有直接等同于控制点。
- 不忽略扩产速度、替代方案和政策约束。
