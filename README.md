# workbuddy-best-practice

> 从一句话办公任务，到可复用的企业 Agent 工作流。  
> From workplace prompting to agentic office automation.

[![Unofficial](https://img.shields.io/badge/WorkBuddy-unofficial-lightgrey)](https://www.codebuddy.cn/docs/workbuddy/Overview)
[![Language](https://img.shields.io/badge/language-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-blue)](README.md)
[![Scope](https://img.shields.io/badge/scope-best%20practice-green)](sources.md)

本仓库是非官方中文 WorkBuddy best-practice 知识库，面向 workplace agent、office automation 和企业内部 Agent 工程化。它不镜像官方文档，而是把官方能力转化为可执行、可验收、可复盘、可治理的任务模板、workflow、case study 和安全清单。

## Start Here

| If you want to... | Read this |
|---|---|
| 了解 WorkBuddy 与普通 Chatbot 的差异 | [WorkBuddy vs Chatbot](00-overview/workbuddy-vs-chatbot.md) |
| 写出可执行、可验收的任务 | [WorkBuddy 任务 Prompt 模板](01-getting-started/task-prompt-template.md) |
| 准备项目上下文但不误解 `.workbuddy/` | [WorkBuddy Context Convention](docs/workbuddy-context-convention.md) |
| 从一次任务沉淀成 workflow | [Research, Plan, Execute, Review, Ship](templates/workbuddy-context/research-plan-execute-review-ship.md) |
| 检查权限、文件和第三方服务风险 | [权限模式与企业安全规范](08-permission-security/permission-modes.md) |
| 直接复制企业模板 | [Templates](templates/README.md) |

> WorkBuddy 官方文档强调工作目录、工作空间和上下文引用；本仓库不假设 `.workbuddy/` 是官方目录规范。

![WorkBuddy 实践工作流二创插图](assets/images/readme-hero-mascot.webp)

## Core Flow

```text
Idea
  -> Task Brief
  -> Context Package
  -> Manual Run
  -> Result Review
  -> Workflow Asset
  -> Expert / Skill / Connector
  -> Automation
  -> Cloud Agent
```

这套方法论借鉴 Claude Code 社区从 “vibe coding” 到 “agentic engineering” 的工程化纪律，但只做方法论对标，不把 `.claude/*`、commands、agents、skills、hooks 或 MCP 写成 WorkBuddy 官方等价机制。

## Capability Map

| Area | What you get | Start with |
|---|---|---|
| Overview | 产品定位、Chatbot 差异、Claude Code 方法论类比 | [00-overview/](00-overview/) |
| Getting started | Task Brief、上下文准备、结果验收 | [01-getting-started/](01-getting-started/) |
| Prompt patterns | 目标、输入、输出、边界、验收写法 | [02-prompt-patterns/](02-prompt-patterns/) |
| Workflows | 从手动任务到可复用 workflow 和 Automation | [03-workflows/](03-workflows/) |
| Experts | Expert / Expert Team 的角色、边界和验收 | [04-experts/](04-experts/) |
| Skills | Skill 来源、权限、脚本、试跑和卸载评估 | [05-skills/](05-skills/) |
| Connectors | 授权账号、数据流、外部写操作和撤销 | [06-connectors/](06-connectors/) |
| Automation | 定时任务、首周监控、失败处理和快速禁用 | [07-automation/](07-automation/) |
| Security | 默认权限、Full Access、工作空间和治理清单 | [08-permission-security/](08-permission-security/) |
| Model / Memory | 模型配置、Memory 使用和隐私边界 | [09-model-memory/](09-model-memory/) |
| Cloud Agent | 企业智能体、Runtime、Session、凭据和发布检查 | [10-cloud-agent/](10-cloud-agent/) |
| Case studies | 文件整理、会议纪要、PPT、数据报告、资讯简报 | [11-case-studies/](11-case-studies/) |

## Learning Path

| Step | Outcome | Guide |
|---|---|---|
| 1 | 建立任务式使用心智 | [WorkBuddy vs Chatbot](00-overview/workbuddy-vs-chatbot.md) |
| 2 | 把模糊需求改写成 Task Brief | [Task Brief Template](templates/task-brief-template.md) |
| 3 | 用 Context Package 显式提供背景 | [Context Package Template](templates/workbuddy-context/context-package-template.md) |
| 4 | 先手动跑通，再检查产物、全部文件、变更和预览 | [结果验收指南](01-getting-started/result-review.md) |
| 5 | 复盘成 workflow，并判断是否需要 Expert / Skill / Connector | [办公 Agent 工程化心智模型](00-overview/mental-model.md) |
| 6 | 对稳定、低歧义、可回滚任务再考虑 Automation | [从手动执行到自动化](03-workflows/manual-to-automation.md) |
| 7 | 对企业级生命周期、渠道、凭据和评测需求再研究 Cloud Agent | [Cloud Agent 实践指南](10-cloud-agent/) |

## Repository Guide

| Path | Purpose |
|---|---|
| [docs/](docs/) | 仓库级说明和非官方实践约定。 |
| [templates/](templates/) | 可复制 Task Brief、review、安全、Skill、Connector、Automation 和 Context Package 模板。 |
| [assets/](assets/) | README 图片、Logo、视觉资产和生成 prompt 记录。 |
| [sources.md](sources.md) | 官方来源、版本敏感事实和 source map。 |
| [changelog-watch.md](changelog-watch.md) | WorkBuddy 官方 Changelog 对本仓库指南的影响记录。 |
| [roadmap.md](roadmap.md) | 仓库维护路线。 |

## Source Boundary

- 官方事实优先来自 [WorkBuddy 官方文档](https://www.codebuddy.cn/docs/workbuddy/Overview) 和 [Changelog](https://www.codebuddy.cn/docs/workbuddy/Changelog)。
- Claude Code best practice 只作为结构、美学和 agentic engineering 方法论参考，不是 WorkBuddy 官方事实来源。
- 第三方文章和 GitHub repo 只能作为“社区观察”或方法论灵感，不能证明 WorkBuddy 官方能力。
- `.workbuddy/` 只可作为团队本地 experimental / repository convention；公开 repo 默认使用 `docs/` 和 `templates/workbuddy-context/` 承载可复用内容。

## Further Reading

- [WorkBuddy 官方简介](https://www.codebuddy.cn/docs/workbuddy/Overview)
- [WorkBuddy 官方更新日志](https://www.codebuddy.cn/docs/workbuddy/Changelog)
- [Sources](sources.md)
- [Review Report](REVIEW_REPORT.md)
- [Claude Code best practice reference](https://github.com/shanraisshan/claude-code-best-practice)

## Disclaimer

本仓库非 WorkBuddy 官方项目，不代表腾讯云、CodeBuddy 或 WorkBuddy 官方立场。WorkBuddy 功能、界面、权限策略、模型能力和价格可能随版本变化，请以官方文档和产品界面为准。使用 Automation、第三方 Skill / Connector、自定义模型 API、Full Access 或 Cloud Agent 前，请自行完成安全、合规和数据隐私评估。
