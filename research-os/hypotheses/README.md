# 假设跟踪系统

## 结论

假设跟踪系统维护 Research OS 的核心判断，记录哪些假设被验证、削弱、推翻或解决，以及置信度为什么变化。

## 状态

- `active`：仍在观察。
- `verified`：被关键证据验证。
- `weakened`：被反证削弱。
- `invalidated`：被推翻。
- `resolved`：已完成研究闭环。

## 使用方式

1. 从洞察卡片 `insights/` 或数据采集层 `data/` 识别需要跟踪的假设。
2. 写入 `hypothesis-ledger.md`。
3. 重大行业变化时更新状态和置信度。
4. 被推翻的假设不得删除，必须保留反证原因。
5. 可影响控制权判断的假设进入 `energy/power-control-rights.md`。

## 更新规则

- 每次更新必须记录 `last_updated`。
- 置信度变化必须记录 `previous_confidence` 和 `confidence_change_reason`。
- 初始假设的 `previous_confidence` 使用 `null`，并说明它是初始记录。

## 非目标

- 不输出股票推荐。
- 不输出交易动作。
- 不输出仓位建议。
