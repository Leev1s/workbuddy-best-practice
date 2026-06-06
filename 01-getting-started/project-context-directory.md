# `.workbuddy` 项目级上下文目录指南

## TL;DR

`.workbuddy/` 是本仓库为了配合 WorkBuddy 工作空间思路而设计的项目级上下文目录。它可以保存任务说明、写作规则、workflow、prompt 模板、审查清单和人工维护的项目记忆，帮助 Agent 在本 repo 中工作时更快理解上下文。它不是 WorkBuddy 官方规范，也不代表 WorkBuddy 会自动读取其中任何文件。

## Official facts

- 根据 WorkBuddy 官方创建任务相关说明，创建任务时可以选择工作目录，WorkBuddy 会基于该目录读取和处理文件。参见 [Create Task](https://www.codebuddy.cn/docs/workbuddy/Create-Task)。
- 根据 WorkBuddy 任务管理相关说明，任务会按工作空间整理任务历史。参见 [Task Management](https://www.codebuddy.cn/docs/workbuddy/Task-Management)。
- 根据 WorkBuddy 权限模式相关说明，工作空间是当前任务主要读取和保存文件的文件夹，默认权限会将工作空间作为安全边界。参见 [Permission Modes](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)。
- 根据 WorkBuddy 记忆功能相关说明，WorkBuddy Memory 是从会话历史中提取事实、偏好、人物关系、近期跟进事项等形成的产品能力。参见 [Memory](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Memory)。

## Practical interpretation

本仓库将 `.workbuddy/` 设计为 project-level context folder for WorkBuddy-oriented workflows。它的作用类似一个稳定的 Context Package：把项目定位、术语、来源规则、写作规范、权限边界、复盘记录和常用 prompt 放在一个可发现的位置。

需要特别区分三件事：

| 概念 | 含义 | 是否官方规范 |
| --- | --- | --- |
| WorkBuddy 工作目录 / 工作空间 | 创建任务时选择、用于读取和保存文件的目录或任务组织边界 | 官方产品概念 |
| WorkBuddy Memory | 产品从会话历史中提取并用于后续任务的背景记忆能力 | 官方产品能力 |
| `.workbuddy/` | 本仓库建议的项目级上下文目录 | 本仓库实践约定，不是官方规范 |

## When to use it

适合在这些场景中维护 `.workbuddy/`：

- 长期维护同一个知识库、课程、SOP 或模板库。
- 团队希望把写作规则、术语、来源策略和交付标准固定下来。
- 多个 Agent 或多人共同维护仓库，需要共享稳定上下文。
- 同一类任务会反复发生，例如新增文章、更新来源、制作培训材料、检查链接。
- 希望把一次性 prompt 升级为可复用 workflow。

不适合把这些内容放入 `.workbuddy/`：

- 本地运行日志、缓存、临时任务产物。
- 未脱敏的客户资料、员工信息、合同、财务数据。
- API Key、Cookie、Token、内网地址、账号密码。
- 私人偏好、私人上下文或只对单次任务有效的临时记忆。

## How to use

### 1. 先把 `.workbuddy/` 当作只读上下文

在任务 prompt 中显式说明：

```text
请先阅读 AGENTS.md、README.md 和 .workbuddy/README.md。
.workbuddy/ 是本仓库的项目级上下文目录，不是 WorkBuddy 官方自动读取机制。
除非我明确要求，请只读取其中的稳定规则，不要修改 .workbuddy/ 文件。
```

### 2. 按文件类型组织稳定材料

建议首版结构：

```text
.workbuddy/
  README.md
  AI_AGENT_INSTRUCTIONS.md
  PROJECT_CONTEXT.md
  TASK_BRIEF.md
  REVIEW_CHECKLIST.md
  prompts/
  workflows/
  output-rules/
  memory/PROJECT_MEMORY.md
```

### 3. 在 Task Brief 中显式引用

```text
项目级上下文：
- 请读取 .workbuddy/PROJECT_CONTEXT.md 理解项目定位。
- 请读取 .workbuddy/AI_AGENT_INSTRUCTIONS.md 理解维护边界。
- 请读取 .workbuddy/REVIEW_CHECKLIST.md 作为交付前检查清单。

操作边界：
- 默认只读 .workbuddy/。
- 不要向 .workbuddy/tmp、logs、cache、private 写入任何文件。
- 如需修改 .workbuddy/ 下的规则文件，请先列出变更计划。
```

## Best practices

- 把 `.workbuddy/` 作为 Context Package，而不是任务产物目录。
- 只提交稳定、可公开、可复用的项目级材料。
- 对规则文件使用清晰标题和短段落，便于 Agent 快速读取。
- 将 prompt、workflow、review checklist 分目录维护，避免一个文件无限膨胀。
- 对“官方事实 / 实践建议 / 风险提醒”做显式区分。
- 更新 `.workbuddy/` 后，同步检查 README 或相关文章是否需要补充导航。

## Common mistakes

- 误写成“WorkBuddy 会自动读取 `.workbuddy/`”。除非官方文档明确说明，否则不能这样写。
- 把 `.workbuddy/memory/PROJECT_MEMORY.md` 当成 WorkBuddy 官方 Memory 的替代品。
- 把一次性临时文件、生成结果、日志、缓存放进 `.workbuddy/`。
- 在 `.workbuddy/` 中保存敏感数据或企业内部凭证。
- 把 Claude Code 的 `.claude/*` 文件系统机制直接映射为 WorkBuddy 官方机制。

## Security / permission notes

- 企业场景建议把 `.workbuddy/` 视为项目规则与上下文资产目录，默认只读。
- Full Access 下尤其要防止 Agent 误改项目级规则、权限说明、项目记忆或安全清单。
- 如果任务需要修改 `.workbuddy/`，应先列出变更文件、变更原因和回滚方式。
- `.gitignore` 应排除 `.workbuddy/tmp/`、`.workbuddy/logs/`、`.workbuddy/cache/`、`.workbuddy/private/` 等本地目录。
- 不要将 `.workbuddy/` 中的内容作为官方承诺、官方配置或官方审计记录。

## Template

```text
本次任务请使用以下项目级上下文：

- AGENTS.md：仓库维护规则。
- README.md：项目定位和目录导航。
- .workbuddy/README.md：.workbuddy 目录定位与边界。
- .workbuddy/PROJECT_CONTEXT.md：项目背景、受众、术语。
- .workbuddy/REVIEW_CHECKLIST.md：交付前检查清单。

请注意：.workbuddy/ 是本仓库实践约定，不代表 WorkBuddy 官方规范；默认只读，除非我明确要求修改。
```

## Further Reading

- [WorkBuddy Overview](https://www.codebuddy.cn/docs/workbuddy/Overview)
- [WorkBuddy Create Task](https://www.codebuddy.cn/docs/workbuddy/Create-Task)
- [WorkBuddy Task Management](https://www.codebuddy.cn/docs/workbuddy/Task-Management)
- [WorkBuddy Permission Modes](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
- [WorkBuddy Memory](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Memory)
- [`.workbuddy/` README](../.workbuddy/README.md)
