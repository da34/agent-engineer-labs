# 01 · 大模型 API Playground

把 LLM 基础里「一次模型调用」的每个环节放到同一个小应用里。

## 要验证什么

能否理解并处理模型调用。

## 需要留下的成果

- [ ] 普通对话
- [ ] 流式响应（SSE / 增量 delta / 中断处理）
- [ ] 结构化输出（JSON Mode / Structured Outputs，含失败处理）
- [ ] 工具调用（Function Calling，完整走通调用请求 → 执行 → 结果回传）
- [ ] Embedding 生成与相似度计算
- [ ] 每次调用的记录：模型、输入、输出、Token 用量、耗时
- [ ] 至少两个模型或两个供应商的 API 差异对比

## 验收

- 能解释一次请求到响应的全过程
- 能说清 `message`、`role`、`tool call`、`tool result`、`stream`、`usage` 的含义
- 能演示完整工具调用
- 能演示结构化输出失败后怎么处理

## 交付物

README、运行说明、示例请求、测试用例。
