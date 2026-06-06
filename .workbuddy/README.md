# .workbuddy Project Context Folder

## What it is

本目录是本仓库的实践约定：a project-level context folder for WorkBuddy-oriented workflows。

它用于存放面向 WorkBuddy 的项目级上下文，包括任务说明、写作规则、工作流、prompt 模板、审查清单和项目记忆。它的目标是帮助 WorkBuddy 在把本 repo 作为工作空间时，更快理解项目定位、边界、术语和交付标准。

## What it is not

- 不是 WorkBuddy 官方规范或必需目录。
- 不代表 WorkBuddy 一定会自动读取本目录或其中任何文件。
- 不等同于 WorkBuddy 官方 Memory 功能。
- 不应被当成本地运行日志、缓存、私人上下文或任务产物目录。

如果未来 WorkBuddy 官方发布 `.workbuddy/` 目录规范，应以官方规范为准，并更新本仓库说明。

## Suggested stable contents

- `AI_AGENT_INSTRUCTIONS.md`：给 Codex / Claude Code / WorkBuddy 类 Agent 的维护规则摘要。
- `PROJECT_CONTEXT.md`：项目定位、读者、术语、来源边界。
- `TASK_BRIEF.md`：当前维护任务的可复制任务简报模板。
- `REVIEW_CHECKLIST.md`：面向本仓库的交付验收清单。
- `prompts/`：稳定、可公开复用的 prompt 模板。
- `workflows/`：稳定、可公开复用的 workflow 说明。
- `output-rules/`：产物命名、目录、引用规则。
- `memory/PROJECT_MEMORY.md`：人工维护的项目级经验记录，不是官方 Memory 数据。

## Safety rules

- 默认把 `.workbuddy/` 视为只读项目上下文；需要修改时，应先说明修改目的。
- 不提交本地生成的临时记忆、运行日志、缓存、任务产物、私人上下文或任何敏感信息。
- 不在本目录保存 API Key、Cookie、内部系统 Token、客户数据、未脱敏员工信息或商业机密。
- 不把第三方 Skill、Connector、MCP server 或脚本默认视为安全。

## Further Reading

- [WorkBuddy Overview](https://www.codebuddy.cn/docs/workbuddy/Overview)
- [WorkBuddy Create Task](https://www.codebuddy.cn/docs/workbuddy/Create-Task)
- [WorkBuddy Permission Modes](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
- [WorkBuddy Memory](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Memory)
- [项目级上下文目录指南](../01-getting-started/project-context-directory.md)
