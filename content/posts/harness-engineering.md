+++
date = '2026-03-23T15:40:00+08:00'
draft = false
title = 'Harness Engineering：让 AI Agent 真正可用的工程实践'
description = '2026 年初，Harness Engineering 突然在 AI 工程圈火了起来。本文系统整理了这个新兴学科的核心概念、方法和实战经验。'
tags = ['AI', 'Agent', 'Engineering', 'Harness Engineering']
categories = ['AI Engineering']
+++

# Harness Engineering：让 AI Agent 真正可用的工程实践

2026 年 2 月，"Harness Engineering"这个词突然在 AI 工程圈子里火了起来。Mitchell Hashimoto 在博客里提了这个说法，OpenAI 紧接着发了百万行代码的实验报告，Martin Fowler 也跟进写了深度分析——几周之内，这个术语就成了讨论 AI Agent 开发绕不开的话题。

## 什么是 Harness Engineering

Harness Engineering 是指围绕 AI Agent（特别是 Coding Agent）设计和构建**约束机制、反馈回路、工作流控制和持续改进循环**的系统工程实践。它解决的核心问题是：当 AI Agent 拥有了强大的代码生成能力后，如何确保其输出的可靠性、一致性和长期可维护性。

"Harness"本意是马具——用来引导强大动物的力量朝有用方向工作，而不是让它横冲直撞。Anthropic 在其文档中推广了这个比喻。

## 为什么它比模型本身更重要

2026 年初，OpenAI 做了一个内部实验：3 名工程师在 5 个月内，通过 Codex Agent 生成了**超过 100 万行代码**，而这 100 万行代码中**没有任何一行是人工手写的**。

关键在于他们实施了一个严格的条件约束——"No Manual Code"。这迫使团队必须创建一个强大的 harness 来确保 agent 的输出质量。

LangChain 的 Deep Agents 团队也用 Harness Engineering 改进方法，让 Terminal Bench 的任务完成率从 52.8% 提升到 66.5%。

Vercel 则将工具从 15 个精简到 2 个，同时优化上下文，结果准确率从 80% 提升到 100%，token 消耗减少了 37%，速度提升了 3.5 倍。

Stripe 的 Minions 系统更是实现了每周超过 1000 个合并的 PR——全部由 Agent 完成。

## 核心组成：Harness 的五大支柱

### 1. 上下文工程（Context Engineering）

确保 Agent 在每一步都能获得精确的信息输入。这包括 RAG（检索增强生成）、记忆管理和上下文窗口优化。

### 2. 工具编排（Tool Orchestration）

提供 Agent 可以调用的工具，并管理这些工具的执行流程。好的工具设计让 Agent 能自动发现错误并纠正。

### 3. 验证循环（Verification Loops）

每次代码变更后自动运行测试套件，确保输出质量。Verification loop 是 Harness 的核心——它创造了一个反馈回路。

### 4. 成本控制（Cost Controls）

监控 token 消耗，防止 Agent 在复杂任务中无限循环消耗资源。成本控制让 Agent 在可接受的资源范围内工作。

### 5. 可观测性（Observability）

记录 Agent 的决策过程和执行轨迹，便于追溯问题和持续优化。

## Harness Engineering vs Context Engineering

| 维度 | Context Engineering | Harness Engineering |
|------|---------------------|---------------------|
| 关注点 | Agent "看到" 什么 | Agent "运行" 的方式 |
| 范围 | 单次推理优化 | 整个系统设计 |
| 作用 | 减少短期幻觉 | 长期可靠性保证 |
| 类比 | 给 CPU 提供更好的数据 | 为计算机提供操作系统 |

Context Engineering 是 Harness Engineering 的子集——它解决的是信息输入问题，而 Harness 解决的是系统可靠性问题。

## 如何开始实施

### 从"强制函数"开始

Mitchell Hashimoto 建议：在一个新模块或重构项目中，采用"No Manual Code"的约束条件。这会强迫你构建可靠的 Harness。

### 定义意图声明

使用高级规格说明、ADR（架构决策记录）和模式验证器，而不是低级别的指令。意图声明让 Agent 理解边界，而不仅仅是执行步骤。

### 把每次失败当作系统问题来永久修复

这是 Harness Engineering 的核心理念。当 Agent 犯错时，不要只是修复输出，而是要工程化地解决根本原因，确保这个错误永远不会再发生。

## 实践案例

GitHub 上已有多个关于 Harness Engineering 的资源：

- [awesome-copilot](https://github.com/github/awesome-copilot) 汇集了大量 Agent Skills 和最佳实践
- Agent Engineering 社区提供了详细的 [Harness Engineering 指南](https://www.agent-engineering.dev/)

## 结论

Harness Engineering 代表了一种范式转变：工程的重点从"写代码"转变为"构建 Agent 能安全运行的环境"。模型能力固然重要，但真正决定 Agent 能否在生产环境可靠运行的，是 Harness 的质量。

如果你正在构建 AI Agent 产品或计划将 Agent 引入企业工作流，Harness Engineering 是必须掌握的核心学科。

---

*本文整理自 2026 年 2-3 月间 Mitchell Hashimoto、Martin Fowler、OpenAI 等多个信息源的讨论和实践。*
