# 研究评审记录

## 结论

`reviews/` 记录每轮观察后的 Review Gate。它用于检查研究链条是否可追溯、可解析、可证伪，并确保输出没有变成股票推荐、交易动作或仓位建议。

## 评审顺序

```text
事实层 -> Schema 层 -> 推理链层 -> 反证层 -> 边界层 -> 修正动作
```

## 使用方式

1. 每轮 `Industry Observer`、`Hypothesis Tracker`、`Control Point Finder` 完成后运行评审。
2. 将评审记录写入本目录。
3. 对 `approved_with_fixes` 或 `blocked` 的问题，先修正对应模块。
4. 修正后重新验证 YAML、source URL、反证和研究边界。

## 非目标

- 不输出股票推荐。
- 不输出交易动作。
- 不输出仓位建议。
