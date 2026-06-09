# Review: 2026-06-09 First Week Energy Observation

review:
  date: 2026-06-09
  scope: first_week_energy_observation
  status: approved_with_fixes

## summary

第一周观察已经形成完整链条：事实进入 `data/`，指标进入 `metrics/`，假设和控制点被同步更新。主要修正是补充 source URL、拆分储能信号、降低算电协同数据优势评分，并把 Review Gate 固化进工作流。

## findings

```yaml
findings:
  - severity: important
    file: data/collection-log.md
    issue: 本轮 weekly signal 原先缺少 source_url，复盘时证据不可直接追溯。
    recommendation: 在 weekly-signal schema 和所有本轮信号中增加 source_url。
  - severity: important
    file: data/collection-log.md
    issue: 甘肃储能市场化推进和山东配储利用率偏低原先合并在同一条 signal 中，日期和证据方向不同。
    recommendation: 拆成市场化推进和利用率反证两条 signal。
  - severity: important
    file: control-rights/candidates.md
    issue: 算电协同候选方向有价值，但第一周证据不足以支撑最高数据优势评分。
    recommendation: 将 data_advantage 从 5 调整为 4，并增加 evidence_gap。
  - severity: medium
    file: hypotheses/hypothesis-ledger.md
    issue: energy-001 和 energy-002 的置信度上调方向合理，但后续需要明确置信度调整阈值。
    recommendation: 下一轮补充 confidence_rules，区分方向性政策、落地数据和客户依赖证据的权重。
```

## verification

```yaml
verification:
  - command: ruby -rdate -ryaml
    result: data、hypotheses 和 control-rights 中的 YAML blocks 可解析。
  - command: rg 股票推荐|交易动作|仓位建议
    result: 仅命中禁止事项，不存在股票推荐或交易动作。
  - command: git diff --check
    result: 无 Markdown 空白错误。
```

## next_action

- 下一轮观察前，先检查每条 weekly signal 是否含 `source_url`。
- 下一轮观察后，必须生成或更新 `reviews/` 评审记录。
- 补充 `confidence_rules`，降低置信度调整的主观性。
