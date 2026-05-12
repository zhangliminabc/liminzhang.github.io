---
title: AI 工具与 API 能力速览（Cursor / Claude / OpenAI）
date: 2026-05-12
tags: [ai, cursor, claude, openai, api]
---

## 摘要

本文基于公开文档与官方更新日志，整理截至 **2026-05-12** 检索时，**Cursor IDE（Agent 与工作流）**、**Anthropic Claude API（提示缓存与工具）**、**OpenAI API（模型与能力摘要）** 的要点，便于自建知识库与团队分享。定价与配额以厂商页面为准，会随时间变化。

## 背景 / 检索范围

- **关键词**：Cursor changelog Agent、Claude API prompt caching tool use、OpenAI API GPT-4.1 o3 models
- **时间窗口**：以官方 changelog / docs 的最近条目为主，不宣称覆盖全部历史版本。
- **主要信源**：见文末「来源与延伸阅读」。

## 功能与要点

### Cursor（IDE 与 Agent）

以下为官方 Changelog 中反复出现的方向性能力（具体版本与细节以页面为准）：

- **Agent 与多代理**：支持并行多 Agent、与工作树（worktree）或远程环境结合的任务拆分；Agents 窗口支持多标签、分块布局（tiled）等，用于同时跟进多条任务线。
- **Composer / 编码模型**：面向代理式编码的模型路线，强调速度与在仓库内完成任务的能力（与具体模型名、版本以 Changelog 为准）。
- **浏览器与自动化**：内置浏览器能力逐步 GA，强调在编辑器内嵌、DOM 选取与自动化工具链；后续版本提到截图坐标点击、错误处理等改进。
- **终端沙箱与网络控制**：沙箱终端、网络与文件权限的细粒度控制，降低 Agent 执行命令的风险面。
- **子代理与 Skills**：子代理（Subagents）可并行、可异步；Skills 以 `SKILL.md` 等形式注入领域知识；市场（Marketplace）侧整合插件、MCP、规则等生态。
- **云端与本地协同**：Cloud Agent、后台 Plan、语音输入等能力在 Changelog 中持续迭代。

**说明**：Cursor 发版频繁，若需写进对客文档，请以对应版本的官方 Changelog 原文为准。

### Anthropic Claude API（提示缓存与工具）

- **Prompt caching（提示缓存）**：对可复用的前缀（如系统提示、工具定义、长文档）做缓存，后续请求命中缓存时可显著降低延迟与费用；官方文档说明缓存控制点（如 `cache_control`）、与消息结构的配合方式及失效条件。
- **Tool use 与缓存**：工具定义可作为可缓存前缀的一部分；变更工具定义、`tool_choice` 等可能使缓存失效，需按文档设计稳定前缀。
- **定价逻辑（概念层）**：缓存写入与读取相对基础输入计价不同，具体数字以 [Pricing](https://www.anthropic.com/pricing) 与文档为准。

### OpenAI API（模型线摘要）

- **GPT-4.1**：官方文档定位为强调指令遵循与工具调用的非推理型强模型之一，并给出上下文长度、计价等参数（以 [Models](https://platform.openai.com/docs/models) 为准）。
- **o 系列推理模型**：`o3` 等面向多步推理与复杂任务；公开材料中强调数学、科学、代码与视觉推理等场景，并介绍与工具、搜索等能力的组合（以官方博客与 API 文档为准）。
- **选用建议**：按任务类型（延迟敏感 / 深度推理 / 工具编排）在控制台与文档中对比上下文、价格与能力边界。

## 来源与延伸阅读

（访问日期：**2026-05-12**）

1. Cursor Changelog（2.0）：https://cursor.com/changelog/2-0  
2. Cursor Changelog（2.4）：https://cursor.com/changelog/2-4  
3. Cursor Changelog（2.5）：https://cursor.com/changelog/2-5  
4. Cursor Changelog（3.0）：https://cursor.com/changelog/3-0  
5. Cursor Changelog（3.1）：https://cursor.com/changelog/3-1  
6. Anthropic — Prompt caching（文档）：https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching  
7. Anthropic — Tool use with prompt caching：https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-use-with-prompt-caching  
8. OpenAI — Models 文档：https://platform.openai.com/docs/models  
9. OpenAI — GPT-4.1：https://platform.openai.com/docs/models/gpt-4.1  
10. OpenAI — o3：https://platform.openai.com/docs/models/o3  
11. OpenAI Blog — Introducing o3 and o4-mini：https://openai.com/blog/introducing-o3-and-o4-mini  

## 变更记录

- **2026-05-12**：首版，基于公开检索整理；未包含各云厂商自有模型与国产助手清单。
