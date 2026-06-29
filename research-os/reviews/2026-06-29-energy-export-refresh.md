# Review: 2026-06-29 Energy Export Refresh

review:
  date: 2026-06-29
  scope: energy_export_refresh
  status: approved_with_limits

## summary

本轮刷新把能源出口从框架补丁推进到可观察链路。新增事实来自 IEA 和 European Commission，覆盖清洁能源技术贸易、海外电网投资缺口和 EU CBAM 正式期。

结论是：能源出口确实是大市场，并且正在受到海外电网瓶颈、贸易壁垒和绿色属性核算共同重塑；但当前证据仍不能证明长期控制权已经形成，因此新增假设 `energy-004` 初始置信度设为 55%，控制点候选 `energy-export-system` 继续维持 low confidence。

## findings

```yaml
findings:
  - severity: important
    file: data/collection-log.md
    issue: 能源出口需要拆分为贸易规模、海外电网瓶颈和绿色属性合规，不能只记录出口额。
    recommendation: 分别记录 energy_equipment_export_orders、overseas_grid_capex、trade_barrier_policy 和 green_power_accounting。
  - severity: important
    file: hypotheses/hypothesis-ledger.md
    issue: 能源出口已经有足够事实建立独立假设，但尚不足以上调为高置信控制权结论。
    recommendation: 新增 energy-004，初始置信度设为 55%。
  - severity: medium
    file: control-rights/candidates.md
    issue: energy-export-system 的市场证据增强，但客户组织依赖证据仍缺失。
    recommendation: 增加证据和反证，维持 low confidence。
  - severity: medium
    file: insights/examples/energy-export-shifts-to-systems.md
    issue: 需要把本轮链路转化为可复用洞察卡片。
    recommendation: 新增洞察卡片，明确出口额不是控制权，海外系统、运维和绿色属性核算才是下一步验证重点。
```

## verification

```yaml
verification:
  - command: ruby -rdate -ryaml
    result: data、metrics、hypotheses、control-rights、insights 和 reviews 中的 YAML blocks 可解析。
  - command: rg 股票推荐|交易动作|仓位建议
    result: 仅命中禁止事项、评审命令说明和边界描述，新增内容不存在股票推荐、交易动作或仓位建议。
  - command: git diff --check
    result: 无 Markdown 空白错误。
```

## next_action

- 回溯海关总署、商务部和行业协会数据，验证能源设备出口价格、毛利、库存和区域结构。
- 跟踪海外电网、配网、变压器、储能并网和微电网项目是否绑定长期运维或软件。
- 跟踪 CBAM、绿电采购、碳足迹和出口产品合规是否进入企业高频工作流。
- 只在出现客户续约、服务收入、软件绑定或切换成本证据后，提高 `energy-export-system` 的控制权置信度。
