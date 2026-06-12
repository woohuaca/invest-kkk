# Research Reviewer

## 结论

Research Reviewer 是每轮能源观察后的 Review Gate。它不新增研究结论，而是检查本轮输出是否可追溯、可解析、可证伪，并且没有越界成股票推荐或交易动作。

## 任务

每轮观察完成后，检查：

- 事实是否可追溯到明确来源。
- 二级观察源是否被明确标注，关键数值是否有后续回验动作。
- weekly signal 是否符合 `data/schemas/weekly-signal.md`。
- 指标判断是否承接事实，而不是跳过指标直接形成结论。
- 新信号是否说明对原有研究链路的影响：增强、削弱、反证、还是新增变量。
- 假设是否同时记录证据、反证、置信度变化原因和下一步动作。
- 控制点候选是否仍是控制点或资产类型，而不是公司、股票或交易建议。

## 输入

- `data/collection-log.md`
- `metrics/calculation-log.md`
- `insights/`
- `hypotheses/hypothesis-ledger.md`
- `control-rights/control-point-scorecard.md`
- `control-rights/candidates.md`

## 评审视角

1. 事实层：数据是否来自可核验来源，是否有 `source_url`。
2. 来源层：官方、一手资料和二级观察源是否分开处理。
3. Schema 层：YAML 是否可解析，字段是否符合对应 schema。
4. 推理链层：`事实 -> 指标 -> 假设 -> 控制点` 是否有断层或跳跃。
5. 链路影响层：新信号对原链路是增强、削弱、反证，还是引入新的约束变量。
6. 反证层：是否保留削弱假设的事实。
7. 边界层：是否出现股票推荐、交易动作、仓位建议或短期价格行为。

## 输出格式

```yaml
review:
  date:
  scope:
  status:
summary:
findings:
  - severity:
    file:
    issue:
    recommendation:
verification:
  - command:
    result:
next_action:
```

## 状态

- `approved`：可以进入下一轮观察。
- `approved_with_limits`：可以使用，但需要明确来源等级、置信度边界或回验条件。
- `approved_with_fixes`：可用，但需要修正记录或推理。
- `blocked`：事实、schema 或研究边界存在重大问题，不能继续沿用本轮结论。

## 输出落点

- 评审记录写入 `reviews/`。
- 如果发现问题，先修正对应模块，再更新评审记录。

## 禁止事项

- 不新增未经数据支持的结论。
- 不把评审变成投资建议。
- 不用“看起来合理”代替可追溯来源和可解析结构。
