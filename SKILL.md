---
name: vibe-coding-prompt-generator
description: Transform rough product ideas into high-quality Codex-ready vibe coding prompts for building apps, websites, tools, SaaS products, AI features, MVPs, prototypes, dashboards, mobile/web experiences, or agent workflows. Use when the user asks to generate, improve, structure, or refine an AI coding prompt from a product concept, startup idea, feature idea, app idea, or vague build request.
---

# Vibe Coding Prompt Generator

## Overview

Use this skill to convert a product idea into a professional development prompt that Codex can execute directly. Prioritize clarity, product thinking, scope control, implementation readiness, and verifiable completion.

Respond in the user's language unless they ask otherwise. For Chinese users, use concise professional Chinese.

## Workflow

1. Detect the user's desired output mode: full by default, quick when they ask for speed, prompt-only when they only want the final prompt, or optimization when they provide an existing prompt to improve.
2. Read the user's idea and judge whether the core product context is sufficient.
3. Classify the product type and use that classification to shape pages, data, AI logic, UI, and technical choices.
4. If information is missing, ask at most 5 questions before generating. Ask only questions that materially improve the final coding prompt.
5. If the user refuses to answer, says to proceed, answers vaguely, or information is still incomplete after follow-up, continue with reasonable assumptions and label them clearly.
6. Produce the required structured analysis, acceptance criteria, and the final copyable vibe coding prompt.

## Output Modes

- **Full mode**: default. Output all required sections.
- **Quick mode**: use when the user asks for a fast, concise, lightweight, or "直接给我" result. Keep each section short but still include the required structure.
- **Prompt-only mode**: use when the user explicitly asks only for the final prompt. Include a one-line assumptions note if needed, then output only the copyable prompt.
- **Optimization mode**: use when the user provides an existing coding prompt. Diagnose gaps, improve scope and execution details, then output the refined copyable prompt.

Do not announce the mode unless it helps the user understand the result.

## Product Type Classification

Before drafting, classify the idea into one primary type and optional secondary types:

- SaaS tool
- AI agent or workflow automation
- AI content generation tool
- Data dashboard or analytics product
- Internal operations tool or CRM
- Marketplace or listing platform
- Community or social product
- Mobile app
- Browser extension
- Developer tool
- Game or interactive experience
- Marketing site with functional conversion flow

Use the type to adjust defaults:

- SaaS/internal tools: prioritize dense workflows, tables, filters, CRUD, permissions when relevant, and practical dashboards.
- AI tools/agents: specify input, model behavior, structured output, human review, retries, and fallback states.
- Dashboards: specify metrics, filters, charts, empty data, mock data, and drill-down behavior.
- Marketplaces/social products: specify profiles, listings/posts, search/discovery, trust states, and moderation boundaries.
- Mobile apps: specify core tabs, gesture-friendly flows, offline or local persistence when useful.
- Browser extensions: specify popup, content script, options page, permissions, and target sites.
- Games/interactives: specify rules, core loop, controls, feedback, win/lose states, and asset needs.
- Marketing sites: include real conversion actions and avoid pure landing-page fluff.

If the type is uncertain, choose the most implementation-useful classification and state it as an assumption.

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

Ask fewer questions when possible:

- Ask 1-2 questions when only one or two high-impact details are missing.
- Ask 3-5 questions only when the idea is very vague.
- If the user sounds impatient or asks to proceed quickly, skip questions and state assumptions.

For each question, optionally add a short reason in parentheses, such as "这会影响页面结构和核心流程". Ask as a compact numbered list. End with a clear option such as: "如果你不想补充，我会基于合理假设直接生成。"

Do not ask about budget, timeline, team size, monetization, deployment, legal constraints, analytics, or edge cases unless the user already raised them.

## Assumption Rules

When proceeding with incomplete information:

- State the assumptions briefly under "需求理解".
- Choose a focused MVP rather than a broad platform.
- Prefer a modern web app unless the user asks for mobile, desktop, extension, or API-only work.
- Recommend AI only when it directly supports the core job-to-be-done. If AI is unnecessary, explicitly say "暂不需要 AI 能力".
- Pick a practical stack that Codex can build quickly, such as Next.js + TypeScript + Tailwind CSS for web apps, unless the user's context suggests another stack.

## MVP Boundary Rules

Make MVP scope sharp enough for one focused Codex build:

- Separate **必须实现** from **暂不实现**.
- Name features that are tempting but should be avoided in v1.
- Prefer one excellent core workflow over many shallow features.
- Avoid authentication, billing, admin panels, multi-tenant permissions, notifications, analytics, and complex integrations unless they are central to the product idea.
- Include mock data or local persistence when it enables a complete demo without backend complexity.
- If the user asks for a huge platform, reduce it to the smallest usable first workflow and call out the later phases.

## AI Capability Rules

When AI is relevant, make the AI behavior buildable:

- Define whether AI is core or assistive.
- Choose the capability pattern: generate, summarize, classify, extract, recommend, search/retrieve, plan, chat, or agentic multi-step action.
- Specify input fields, context used, output schema, user controls, and edit/approve flow.
- Specify loading, partial output, low-confidence, refusal, timeout, and retry behavior.
- Prefer structured outputs when the result feeds UI or data storage.
- Avoid adding AI when deterministic UI, forms, filters, rules, or templates solve the problem better.

## Design Quality Rules

For UI guidance, specify:

- Layout density and information hierarchy
- Navigation model
- Component style for forms, tables, cards, lists, dashboards, editors, or canvases
- Color and typography direction without overusing one-hue palettes
- Empty, loading, error, and success states
- Responsive behavior for desktop and mobile
- Reference products as inspiration only; describe what to borrow from them

For operational tools, keep the interface quiet, efficient, and scannable. For creative or consumer products, allow more expressive visuals when it supports the product.

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
11. 验收标准
12. 最终可复制vibe coding prompt

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

Include:

- 必须实现
- 暂不实现
- 容易误做但应避免
- 后续版本可扩展

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

Define practical entities and fields. Use simple TypeScript-like shapes or database-table style. Include relationships, status enums, local/mock storage expectations, and CRUD behavior where helpful.

### 技术栈

Recommend a concrete stack, including frontend, backend/API, storage, styling, AI SDK/model if needed, and testing/verification. Keep choices realistic for Codex.

### UI风格

Specify visual direction, layout density, navigation, component feel, color/typography guidance, interaction tone, responsive behavior, and reference products if provided or inferable.

### 验收标准

Define measurable completion criteria:

- Functional acceptance: what user actions must work
- UI acceptance: what states and responsive layouts must exist
- Data acceptance: what persistence, mock data, or validation must work
- AI acceptance: expected input/output/fallback behavior if AI is used
- Engineering acceptance: lint/test/build/dev-server or browser verification expectations

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
- Acceptance criteria
- Implementation expectations
- Verification expectations

The final prompt should tell Codex to implement the product, not merely analyze it. Include instructions to inspect the existing repo first, follow local conventions, keep the scope focused, run relevant checks, and start or provide the local dev URL when applicable.

## Engineering Execution Requirements

The final prompt must instruct Codex to:

- Inspect the existing repository before editing.
- Follow existing framework, component, styling, routing, and data patterns when present.
- Avoid rewriting unrelated files or introducing unnecessary dependencies.
- Implement the smallest complete MVP that satisfies the core workflow.
- Include realistic mock data or local persistence when no backend is required.
- Add empty, loading, error, success, and validation states where relevant.
- Keep UI responsive and ensure text does not overflow controls.
- Run relevant checks such as lint, tests, typecheck, or build.
- For frontend apps, start the dev server and provide the local URL when feasible.
- If checks cannot run, explain the blocker and what remains unverified.

## Final Prompt Template

Use this structure for the copyable prompt, adapting details to the product:

```text
你是 Codex，请把下面的产品想法实现为一个可运行的 MVP。

产品背景：
[用 2-4 句说明目标用户、问题、产品定位和核心价值。]

产品类型：
[写出主要产品类型，以及这个类型对页面、数据和交互的影响。]

MVP 范围：
- 必须实现：[功能 1、功能 2、功能 3]
- 暂不实现：[本次不做的功能]
- 避免误做：[容易膨胀但不该做的内容]

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

验收标准：
- 功能：[核心动作必须可完成]
- UI：[响应式、状态、可读性要求]
- 数据：[存储、校验、mock data 或 CRUD 要求]
- AI：[如果有 AI，说明输入输出和失败兜底要求]
- 工程：[lint/test/build/dev server/browser verification 要求]

实现要求：
- 先检查当前代码库结构，沿用已有技术栈、组件和样式约定。
- 以可运行 MVP 为目标，避免实现超出范围的功能。
- 不重写无关文件，不引入不必要依赖。
- 补齐必要的空状态、加载状态、错误状态、成功状态、表单校验和基础响应式布局。
- 保持代码清晰，必要时添加少量注释。
- 完成后运行相关 lint/test/build 检查；如果是前端应用，启动本地开发服务并提供访问地址。
```
