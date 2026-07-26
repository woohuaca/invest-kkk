# Review: 2026-07-26 Energy Export Update

review:
  date: 2026-07-26
  scope: energy_export_update
  status: approved_with_limits

## summary

本轮更新把 2026 年上半年出口数据接入 `energy-004`。新增事实显示机电产品、锂电池、风力发电机组和汽车出口继续高增，能源制造外溢能力仍强。

结论是：能源出口的市场规模和产品出海证据增强，但控制权证据没有同步增强。新增事实仍主要证明设备出口能力，不证明海外客户已经形成系统依赖、软件绑定、运维收入或高切换成本。因此 `energy-004` 置信度维持 55%。

## review_logic

1. 来源层：本轮使用 SCIO 和新华社公开来源，属于可追溯公开来源。
2. 事实层：机电产品、锂电池、风力发电机组和汽车出口高增只记录为产品出口事实。
3. 指标层：更新 `energy_equipment_export_orders` 和 `export_customer_dependency`，不新增孤立指标。
4. 假设层：`energy-004` 只更新证据和反证，不上调置信度。
5. 控制权层：`energy-export-system` 继续保持 low confidence，等待服务收入、软件绑定、客户续约和数据闭环证据。
6. 边界层：没有股票推荐、交易动作或仓位建议。

## findings

```yaml
findings:
  - severity: important
    file: hypotheses/hypothesis-ledger.md
    issue: 出口高增增强的是市场规模和制造能力，不是海外客户控制权。
    recommendation: energy-004 维持55%，除非出现海外服务收入、软件绑定、客户续约或高切换成本证据。
  - severity: important
    file: observations/energy-export-watchlist.md
    issue: 观察池需要继续防止从出口额增长跳到投资结论。
    recommendation: 下一轮优先回溯 A 类观察对象的服务收入、运维网络、软件平台和客户依赖证据。
  - severity: medium
    file: control-rights/candidates.md
    issue: energy-export-system 的新增证据仍偏产品层。
    recommendation: 候选维持 low confidence，并保留价格竞争、本地化和客户关系被当地主体吸收的反证。
```

## verification

```yaml
verification:
  - command: ruby -rdate -ryaml
    result: data、hypotheses、control-rights、observations 和 reviews 中的 YAML blocks 可解析。
  - command: rg 股票推荐|交易动作|仓位建议
    result: 仅命中禁止事项、评审边界和研究边界描述。
  - command: git diff --check
    result: 无 Markdown 空白错误。
```

## next_action

- 对 A 类观察对象逐项找 `exposure proof`：海外订单质量、毛利、服务收入、软件绑定、客户续约、备件网络和合规工作流。
- 把出口数据和控制权证据分开记录，避免用出口额替代客户依赖判断。
