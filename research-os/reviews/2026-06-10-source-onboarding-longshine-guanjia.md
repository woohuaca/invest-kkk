# Review: 2026-06-10 Longshine Guanjia Source Onboarding

review:
  date: 2026-06-10
  scope: source_onboarding_longshine_guanjia
  status: approved_with_limits

## summary

朗新能源研究院「观价」可以作为 Energy Research OS 的二级市场观察源。它的价值不在于替代官方数据，而在于更快暴露省级现货市场的价差、波动、区域分化和预测变量，帮助系统发现调度、EMS 和 VPP 的控制权信号。

## findings

```yaml
findings:
  - severity: important
    file: data/sources.md
    issue: 公众号和机构研究源如果不区分来源等级，容易被误用为官方事实源。
    recommendation: 将朗新能源研究院「观价」标注为二级观察源，并要求关键数值回溯交易中心、监管机构或官方披露验证。
  - severity: important
    file: metrics/metric-catalog.md
    issue: 原指标目录没有单独承接省级现货市场的日前-实时价差、燃煤基准价位置和区域分化。
    recommendation: 增加 day_ahead_realtime_spread、spot_price_vs_coal_benchmark、regional_price_divergence 和 market_volatility。
  - severity: medium
    file: agents/industry-observer.md
    issue: 每周观察流程原先没有明确处理二级观察源的置信度边界。
    recommendation: 增加来源等级判断，二级观察源只能形成待验证信号。
```

## verification

```yaml
verification:
  - command: ruby -rdate -ryaml
    result: data、agents、hypotheses、control-rights 和 reviews 中的 YAML blocks 可解析。
  - command: rg 股票推荐|交易动作|仓位建议
    result: 仅命中禁止事项和评审命令说明，新增内容不存在股票推荐、交易动作或仓位建议。
  - command: git diff --check
    result: 无 Markdown 空白错误。
```

## next_action

- 后续连续观察至少两期「观价」内容，确认该源是否稳定覆盖省级现货价格、价差和预测变量。
- 对关键价格数据回溯电力交易中心、监管机构或官方公开披露，避免把二级源预测当作已验证事实。
