# Review: 2026-07-22 Energy Observation Refresh

review:
  date: 2026-07-22
  scope: energy_observation_refresh
  status: approved_with_limits

## summary

本轮刷新把观察从“工业控制接入”扩展回能源系统主线。新增事实全部来自国家能源局和12398通报，覆盖迎峰度夏负荷、1-6月全社会用电量、电力市场交易、调度指令执行、配网投诉、能源数据分级和6月新增新能源项目。

结论是：调度层证据小幅增强，因为电力市场交易深度提高，且12398通报显示调度指令具备监管可执行性；但峰值负荷创新高期间未触发需求响应或有序用电，VPP实际调用收益仍未验证。`energy-002` 由70%小幅上调至72%，`energy-001` 维持75%，`energy-003` 维持65%。

## review_logic

1. 来源层：本轮事实来自国家能源局官网和12398通报，属于官方或一手来源。
2. 事实层：峰值负荷、用电量、市场交易、调度违规、数据分级和新增新能源项目分别拆开处理。
3. 指标层：新增 `peak_load_pressure` 和 `dispatch_instruction_compliance`，并更新 data_center_load_growth、charging_load_growth、dispatch_market_reform、grid_connection_delay、data_feedback_loop 和 renewable_penetration。
4. 假设层：只对有交易深度和监管执行证据支撑的 energy-002 小幅上调；对 stable capacity 和 EMS/VPP 组织依赖保持克制。
5. 控制权层：dispatch-layer 证据增强，但 VPP 和 EMS 仍需要实际调用、客户授权和数据闭环案例。
6. 边界层：没有股票推荐、交易动作或仓位建议。

## findings

```yaml
findings:
  - severity: important
    file: hypotheses/hypothesis-ledger.md
    issue: 全国负荷创新高增强稳定容量和调度观察，但未触发需求响应和有序用电，不能单向提高稳定容量稀缺置信度。
    recommendation: energy-001 维持75%，继续观察需求响应触发、峰时价差和局部停电。
  - severity: important
    file: hypotheses/hypothesis-ledger.md
    issue: 电力市场交易高增和调度指令违规整改让调度层证据从政策目标推进到交易深度和执行约束。
    recommendation: energy-002 小幅上调至72%，但保留现货占比和执行风险反证。
  - severity: medium
    file: control-rights/candidates.md
    issue: 充换电和数据中心用电高增继续增强 EMS/VPP 需求背景，但没有证明客户闭环控制授权或实际调用收益。
    recommendation: VPP 和 EMS 维持 medium confidence，下一轮优先找需求响应履约、OT接入和数据授权案例。
```

## verification

```yaml
verification:
  - command: ruby -rdate -ryaml
    result: data、hypotheses、control-rights 和 reviews 中的 YAML blocks 可解析。
  - command: rg 股票推荐|交易动作|仓位建议
    result: 仅命中禁止事项、评审边界和研究边界描述。
  - command: git diff --check
    result: 无 Markdown 空白错误。
```

## next_action

- 迎峰度夏期间继续跟踪负荷新高是否触发需求响应、有序用电、现货价差或辅助服务收益。
- 对调度指令执行建立观察链：AGC/AVC 投入、人工/自动控制边界、违规整改和并网主体运行管理。
- 对 EMS/VPP 保持证据门槛：只有出现实际调用收益、闭环控制授权、数据授权和客户工作流依赖，才上调组织依赖判断。
