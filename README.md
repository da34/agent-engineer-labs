# Agent Engineer Labs

跟着一条学习路线，从「看懂一次模型调用」走到「做出一个别人能运行和使用的 Agent 服务」。

本仓库是 [Chasen《「万字总结」- 我偷来了一份成为 Agent 工程师的学习线路》](https://x.com/chasen_liao/status/2109081301819310578) 这篇文档的实战落地：把知识点、学习文档、项目要求和验收标准对齐到可以真正交付的代码上。

> 知识点与项目要求来自原文档整理的材料，这里做的是把它们变成一个个跑得起来、解释得清楚、验证得了的实践项目。

## 这条路线在解决什么

围绕已有模型，把**检索、工具、上下文和业务系统**接起来，让 Agent 能完成具体任务。每一步都要能回答同一个问题：

> 这一部分学完之后，我能做出什么，又该怎么验证自己确实学会了？

## 学习路线

1. **LLM 基础**：先把一次模型调用看明白（Transformer、Token 与上下文窗口、采样参数）
2. **模型类型和 API 协议**：Chat / Reasoning / 多模态 / Embedding / Rerank，Chat Completions / Responses / Messages
3. **Prompt Engineering**：把任务、材料和验收要求说清楚（贯穿后面所有项目）
4. **RAG**：把资料变成可检索、可引用的证据
5. **Agent 应用**：理解循环，再补齐状态、上下文与边界
6. **后端工程**：让 Agent 成为可以运行和维护的服务

## 五个可交付项目

| # | 项目 | 主要验证什么 | 需要留下的成果 | 目录 |
|---|---|---|---|---|
| 01 | 大模型 API Playground | 能否理解并处理模型调用 | 对话、流式、结构化输出、工具调用、Embedding、调用记录与 API 差异对比 | [`01-api-playground`](./01-api-playground) |
| 02 | RAG + Tool Calling Agent | 能否用资料和工具完成问答 | 文档处理、来源引用、至少 2 个工具、不少于 20 条测试问题与失败分析 | [`02-rag-tool-agent`](./02-rag-tool-agent) |
| 03 | 简化 Coding Agent | 能否理解并修改 Agent Harness | 核心循环、工具执行、权限与上下文管理、可验证的机制改动 | [`03-coding-agent`](./03-coding-agent) |
| 04 | AI 服务后端系统 | 能否把 AI 能力做成服务 | API、数据持久化、后台任务、Docker Compose、测试与基础 CI | [`04-ai-backend`](./04-ai-backend) |
| 05 | 综合个人 Agent | 能否把各部分组合起来 | 可追踪的完整任务流程、会话与状态设计、运行说明和失败处理 | [`05-personal-agent`](./05-personal-agent) |

推进建议：

- Prompt 设计贯穿所有项目，每个项目至少保留 3 组「修改前 / 修改后」的对比。
- 已经会后端，可以从 API Playground 直接起步，同时补模型基础。
- 编程基础还不稳，就先补 Python、Git、HTTP、JSON 和基本接口开发，再进入第一阶段。
- 向量索引算法、Advanced RAG、复杂记忆、Kubernetes、微服务，等基础项目产生真实需求后再深入。

## 每个项目的交付标准

每个项目的 README 都应该能回答清楚：

1. **输入是什么** —— 用户 / 调用方给它什么
2. **输出是什么** —— 它交付什么
3. **成功标准是什么** —— 怎样算做对了
4. **哪里容易失败** —— 已知的边界和异常
5. **失败后怎样处理** —— 重试、降级、报错还是人工介入

同时把**代码、文档、运行说明和相关测试**一起放进仓库，别人拿到链接能自己跑起来。

## 仓库结构

```text
agent-engineer-labs/
├── README.md            # 路线总览与进度
├── 01-api-playground/   # 大模型 API Playground
├── 02-rag-tool-agent/   # RAG + Tool Calling Agent
├── 03-coding-agent/     # 简化 Coding Agent
├── 04-ai-backend/       # AI 服务后端系统
└── 05-personal-agent/   # 综合个人 Agent
```

## 怎么用这个仓库

- 每个目录下有独立的 README，记录该项目的目标、验收标准和进度。
- 学到哪一步就在对应目录里动手，别只收藏仓库。
- 每段 AI 帮忙生成的实现，都亲手跑一个正常案例和一个异常案例，再试着解释执行过程。

## 原始出处

- 原文：<https://x.com/chasen_liao/status/2109081301819310578>（作者 [@chasen_liao](https://x.com/chasen_liao)，2026-10-11）
- 本仓库仅用于个人学习与实践，材料版权归原作者所有。
