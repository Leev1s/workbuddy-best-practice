# WorkBuddy Context Convention

## TL;DR

WorkBuddy 官方文档强调的是工作目录、工作空间、上下文引用、权限模式和产品层面的 Memory。本仓库不假设 `.workbuddy/` 是 WorkBuddy 官方目录规范、强制目录或推荐目录。

本仓库仍保留“Context Package”方法论：把任务背景、资料、术语、规则、prompt、workflow 和验收标准组织成一组可显式引用的文件。公开仓库中的推荐位置是 [templates/workbuddy-context/](../templates/workbuddy-context/)，而不是默认创建 `.workbuddy/`。

## What Is Official

根据 WorkBuddy 官方文档，可以稳定引用的概念包括：

| Official concept | Practical meaning |
|---|---|
| 工作目录 / 工作空间 | 创建任务时选择或管理的文件范围，影响 WorkBuddy 读取、处理和保存文件的位置。 |
| 上下文引用 | 创建任务时通过 `@` 引用文件、上传文件、粘贴截图或补充说明来提供上下文。 |
| 权限模式 | 默认权限和 Full Access / 完全放开决定高风险动作是否需要确认。 |
| Memory | 产品从会话历史中提取个人信息、偏好、人物关系、近期跟进事项等背景信息，并允许用户查看、编辑、删除或关闭。 |

## What This Repo Recommends

对于公开 repo，更稳妥的做法是把可复用上下文作为普通文档或模板管理：

```text
docs/
  workbuddy-context-convention.md
templates/
  workbuddy-context/
    context-package-template.md
    repository-maintenance-brief.md
    repository-review-checklist.md
    maintenance-prompts.md
    research-plan-execute-review-ship.md
```

这样做的好处：

- 不暗示 WorkBuddy 会自动读取某个隐藏目录。
- 读者可以清楚看到哪些内容是公开模板，哪些内容需要复制到自己的项目中。
- 企业团队可以按内部规范选择放在 `docs/`、`templates/`、知识库、SOP 系统或本地实验目录中。

## If A Team Uses `.workbuddy/`

团队可以在自己的私有项目中把 `.workbuddy/` 当成本地实验目录或 repository convention，但需要满足这些条件：

- 明确标注 experimental / repository convention。
- 在 prompt 中显式说明要读取哪些文件，不假设 WorkBuddy 自动读取。
- 不把其中的 Markdown memory 文件混同为 WorkBuddy 官方 Memory。
- 不提交临时记忆、运行日志、缓存、任务产物、私人上下文或敏感数据。
- 如用于公开 repo，应优先改放到 `templates/workbuddy-context/` 或 `docs/`。

## Common Mistakes

- 把 `.workbuddy/` 写成官方目录规范。
- 声称 WorkBuddy 会自动读取 `.workbuddy/AI_AGENT_INSTRUCTIONS.md`。
- 把 `.workbuddy/memory/PROJECT_MEMORY.md` 写成官方 Memory 能力。
- 把一次性会话记录、客户资料、API Key、Cookie 或企业内部凭据写入项目上下文目录。
- 用本仓库的 Context Package 约定替代 WorkBuddy 官方权限模式、工作空间和 Memory 设置。

## Security / Permission Notes

Context Package 应默认只保存稳定、可公开、可审查的材料。涉及客户数据、员工信息、合同、财务、Token、Cookie、API Key、模型配置或第三方授权凭据时，不应写入公开仓库模板，也不应依赖 Agent 自行判断是否可公开。

使用 Full Access、Skill、Connector、Automation 或 Cloud Agent 时，应把 Context Package 视为输入说明，而不是安全控制本身。真正的安全边界仍来自工作空间隔离、权限模式、人工确认、备份、撤销授权和验收流程。

## Further Reading

- [WorkBuddy 官方文档：创建任务](https://www.codebuddy.cn/docs/workbuddy/Create-Task)
- [WorkBuddy 官方文档：任务管理](https://www.codebuddy.cn/docs/workbuddy/Task-Management)
- [WorkBuddy 官方文档：两个权限模式](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
- [WorkBuddy 官方文档：记忆](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Memory)
- [Context Package templates](../templates/workbuddy-context/README.md)
