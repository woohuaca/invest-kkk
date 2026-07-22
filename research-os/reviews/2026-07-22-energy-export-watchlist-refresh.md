# Review: 2026-07-22 Energy Export Watchlist Refresh

review:
  date: 2026-07-22
  scope: energy_export_watchlist_refresh
  status: approved_with_limits

## summary

本轮刷新把能源出口从宏观观察推进到观察标的池。新增文件 `observations/energy-export-watchlist.md`，第一批只放控制点和资产类型，不直接放股票或交易标的。

结论是：能源出口可以进入观察池，但必须保持 `approved_with_limits`。当前证据足以支持研究优先级，不足以支持投资结论。观察重点从出口额转向海外系统交付、长期运维、EMS/VPP、绿色属性核算、客户续约和切换成本。

## review_logic

1. 来源层：使用 IEA、European Commission、SCIO 等公开权威来源作为观察触发，不使用二级叙事替代公司级证据。
2. 标的层：先放控制点和资产类型，暂不直接放具体股票，避免从宏观主题跳到投资结论。
3. 指标层：所有观察对象都必须链接到既有指标，如 `overseas_grid_capex`、`trade_barrier_policy`、`overseas_om_network`、`export_customer_dependency`。
4. 假设层：本轮不调整 `energy-004` 置信度，仍以 55% 作为早期假设。
5. 控制权层：只把 A 类对象视为立即研究候选，不视为已验证控制权资产。
6. 边界层：本轮没有股票推荐、交易动作或仓位建议。

## findings

```yaml
findings:
  - severity: important
    file: observations/energy-export-watchlist.md
    issue: 观察标的池如果直接列公司，容易把能源出口主题误读为投资推荐。
    recommendation: 第一版只放控制点和资产类型，并要求公司级观察必须补充 exposure proof。
  - severity: important
    file: observations/energy-export-watchlist.md
    issue: 出口额增长本身不能证明控制权。
    recommendation: 每个观察对象都必须写清楚 evidence_needed 和 counter_evidence。
  - severity: medium
    file: hypotheses/hypothesis-ledger.md
    issue: 本轮刷新增强了观察执行力，但没有新增足以改变 energy-004 置信度的客户依赖证据。
    recommendation: 维持 energy-004 55%，等待服务收入、软件绑定、客户续约或切换成本证据。
```

## verification

```yaml
verification:
  - command: ruby -rdate -ryaml
    result: research-os 中的 YAML blocks 可解析。
  - command: rg 股票推荐|交易动作|仓位建议
    result: 仅命中禁止事项、评审命令说明和边界描述，新增内容不存在股票推荐、交易动作或仓位建议。
  - command: git diff --check
    result: 无 Markdown 空白错误。
```

## next_action

- 选择 6-8 个公司级观察对象，但每个对象必须先补 `exposure proof`。
- 对 A 类观察对象优先做来源回溯：海外订单、毛利、服务收入、软件绑定、客户续约和合规工作流。
- 不把“出口增长快”作为控制权结论，除非能证明客户依赖或数据闭环。
