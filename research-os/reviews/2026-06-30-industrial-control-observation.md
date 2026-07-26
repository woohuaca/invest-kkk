# Review: 2026-06-30 Industrial Control Observation

review:
  date: 2026-06-30
  scope: industrial_control_observation
  status: approved_with_limits

## summary

本轮观察把工业控制接入从框架判断推进到可跟踪变量。新增信号来自 NIST SP 800-82 Rev.4 预草案征求意见和一篇公网 OT 暴露面研究，结论是：EMS/VPP 要进入真实控制层，必须处理 OT 安全、边缘响应、工业协议、控制权限和审计边界；但这些证据仍只证明前置约束和攻击面，不证明客户已经授予闭环控制权限或形成稳定收益，因此 `energy-003` 置信度维持 65%。

## review_logic

1. 来源层：NIST 属于官方/一手标准修订信号；公网 OT 暴露面研究属于研究型来源，需作为中等置信信号使用。
2. 事实层：NIST 证明 OT 指南正在纳入新技术和威胁环境；暴露面研究证明公网 OT 接入存在现实攻击面。
3. 指标层：两条事实都汇入 `industrial_control_integration`，没有新增孤立指标。
4. 假设层：只更新 `energy-003` 的支撑证据、反证和下一步动作，不上调置信度。
5. 控制权层：EMS/VPP 候选补充了 OT 接入深度和安全边界，保持 medium confidence。
6. 边界层：本轮没有股票推荐、交易动作或仓位建议。

## findings

```yaml
findings:
  - severity: important
    file: metrics/calculation-log.md
    issue: 工业控制接入不能只被当作功能增强，它同时带来安全、停线和授权约束。
    recommendation: 保留只读采集、优化建议、人工执行和闭环控制权限四层区分。
  - severity: important
    file: hypotheses/hypothesis-ledger.md
    issue: NIST 与公网 OT 暴露面研究增强了 industrial_control_integration 的研究必要性，但还没有客户依赖和收益证据。
    recommendation: energy-003 保持 65%，只更新证据、反证和 next_action。
  - severity: medium
    file: control-rights/candidates.md
    issue: EMS/VPP 候选需要把安全网关、分区隔离和审计能力纳入能力边界。
    recommendation: 后续案例优先验证 OT 接入方式，而不是只看接入设备数量。
```

## verification

```yaml
verification:
  - command: ruby -rdate -ryaml
    result: data、hypotheses、control-rights 和 review 中的 YAML blocks 可解析。
  - command: rg 股票推荐|交易动作|仓位建议
    result: 仅命中禁止事项、评审边界和研究边界描述。
  - command: git diff --check
    result: 无 Markdown 空白错误。
```

## next_action

- 下一轮寻找企业级 EMS/VPP 项目是否披露 PLC/SCADA/MES 接入方式。
- 对案例按只读采集、优化建议、人工执行和闭环控制权限分层。
- 同时记录安全分区、边缘网关、最小权限、审计和停线风险，避免把“接入设备多”误判为组织依赖。
