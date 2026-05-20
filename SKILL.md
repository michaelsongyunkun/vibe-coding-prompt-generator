---
name: vibe-coding-prompt-generator
description: Transform rough product ideas into high-quality Codex-ready vibe coding prompts for building apps, websites, tools, SaaS products, AI features, MVPs, prototypes, dashboards, mobile/web experiences, or agent workflows. Use when the user asks to generate, improve, structure, or refine an AI coding prompt from a product concept, startup idea, feature idea, app idea, or vague build request.
---

# Vibe Coding Prompt Generator

## Overview

Use this skill to convert a product idea into a professional development prompt that Codex can execute directly. Prioritize clarity, product thinking, scope control, and implementation readiness.

Respond in the user's language unless they ask otherwise. For Chinese users, use concise professional Chinese.

## Workflow

1. Read the user's idea and judge whether the core product context is sufficient.
2. If enough information exists, generate the full output immediately.
3. If information is missing, ask at most 5 questions before generating. Ask only questions that materially improve the final coding prompt.
4. If the user refuses to answer, says to proceed, answers vaguely, or information is still incomplete after follow-up, continue with reasonable assumptions and label them clearly.
5. Produce the required structured analysis and the final copyable vibe coding prompt.

## Sufficiency Check

Consider the input sufficient when you can infer:

- Target users
- Specific problem to solve
- Core user workflow
- Whether AI capability is needed
- Desired visual style or reference product
- Rough MVP boundary

Do not over-question. If 3 or more of these are clear or strongly inferable, proceed and fill gaps with assumptions.

## Follow-Up Questions

When information is insufficient, ask no more than 5 questions total. Questions must stay within these topics:

1. 产品目标用户是谁？
2. 这个产品解决什么具体问题？
3. 用户完成任务的核心流程是什么？
4. 是否需要 AI 能力？
5. 希望做成什么视觉风格或参考产品？

Ask as a compact numbered list. End with a clear option such as: "如果你不想补充，我会基于合理假设直接生成。"

Do not ask about budget, timeline, team size, monetization, deployment, legal constraints, analytics, or edge cases unless the user already raised them.

## Assumption Rules

When proceeding with incomplete information:

- State the assumptions briefly under "需求理解".
- Choose a focused MVP rather than a broad platform.
- Prefer a modern web app unless the user asks for mobile, desktop, extension, or API-only work.
- Recommend AI only when it directly supports the core job-to-be-done. If AI is unnecessary, explicitly say "暂不需要 AI 能力".
- Pick a practical stack that Codex can build quickly, such as Next.js + TypeScript + Tailwind CSS for web apps, unless the user's context suggests another stack.

## Required Output

Always output these sections in this order:

1. 需求理解
2. 产品定位
3. MVP范围
4. 页面结构
5. 功能模块
6. 用户流程
7. AI能力逻辑
8. 数据结构
9. 技术栈
10. UI风格
11. 最终可复制vibe coding prompt

Each section should be concrete enough to guide implementation. Avoid generic filler.

## Section Guidance

### 需求理解

Summarize what the user wants in 3-6 bullets. Include assumptions only when needed.

### 产品定位

Define:

- Target user
- Core scenario
- Main value proposition
- What the product is not trying to do in the MVP

### MVP范围

List the must-have features and explicitly exclude nice-to-have features that would bloat the first build.

### 页面结构

Define pages or major views. For each page, include purpose and key UI elements.

### 功能模块

Group features by module. Include states such as empty, loading, error, success, and edit/delete when relevant.

### 用户流程

Describe the happy path step by step. Include at least one recovery path if failure is likely.

### AI能力逻辑

If AI is needed, define:

- Input
- Processing logic
- Output
- User controls
- Failure/fallback behavior

If AI is not needed, explain why and keep the implementation non-AI.

### 数据结构

Define practical entities and fields. Use simple TypeScript-like shapes or database-table style. Include relationships where helpful.

### 技术栈

Recommend a concrete stack, including frontend, backend/API, storage, styling, AI SDK/model if needed, and testing/verification. Keep choices realistic for Codex.

### UI风格

Specify visual direction, layout density, component feel, color/typography guidance, interaction tone, and reference products if provided or inferable.

### 最终可复制vibe coding prompt

Create a self-contained prompt that can be pasted directly into Codex. It must include:

- Role and goal
- Product context
- MVP scope
- Pages/views
- Features
- User flow
- AI logic if any
- Data model
- Tech stack
- UI direction
- Implementation expectations
- Verification expectations

The final prompt should tell Codex to implement the product, not merely analyze it. Include instructions to inspect the existing repo first, follow local conventions, keep the scope focused, run relevant checks, and start or provide the local dev URL when applicable.

## Final Prompt Template

Use this structure for the copyable prompt, adapting details to the product:

```text
你是 Codex，请把下面的产品想法实现为一个可运行的 MVP。

产品背景：
[用 2-4 句说明目标用户、问题、产品定位和核心价值。]

MVP 范围：
- [必须实现的功能 1]
- [必须实现的功能 2]
- [必须实现的功能 3]

页面结构：
- [页面/视图 1]：[用途和关键元素]
- [页面/视图 2]：[用途和关键元素]

核心功能模块：
- [模块 1]：[行为、状态、边界]
- [模块 2]：[行为、状态、边界]

用户流程：
1. [步骤 1]
2. [步骤 2]
3. [步骤 3]

AI 能力逻辑：
[如果需要 AI，写清输入、处理、输出、失败兜底；如果不需要，写“本 MVP 暂不需要 AI 能力”。]

数据结构：
[写出实体、字段、关系或 TypeScript interface。]

技术栈建议：
[写出框架、语言、样式、存储、AI SDK/模型、测试方式。]

UI 风格：
[写出视觉风格、布局、组件、颜色、字体、动效、参考产品。]

实现要求：
- 先检查当前代码库结构，沿用已有技术栈、组件和样式约定。
- 以可运行 MVP 为目标，避免实现超出范围的功能。
- 补齐必要的空状态、加载状态、错误状态和基础响应式布局。
- 保持代码清晰，必要时添加少量注释。
- 完成后运行相关 lint/test/build 检查；如果是前端应用，启动本地开发服务并提供访问地址。
```
