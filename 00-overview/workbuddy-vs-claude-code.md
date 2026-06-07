# WorkBuddy vs Claude Code mental model

## TL;DR

本仓库借鉴 Claude Code best practice 的工程化组织方式，但不照搬 Claude Code 的产品机制。Claude Code 偏 codebase / repo engineering；WorkBuddy 偏 workplace / local files / office automation / enterprise workflow。下面的映射只是方法论类比，不是官方功能等价关系。

## Official facts

- WorkBuddy 官方文档描述的核心对象包括任务、结果区、专家、技能、连接器、自动化、权限模式、记忆、模型配置和企业智能体 / Cloud Agent。
- Claude Code best practice 是本仓库的组织灵感来源，不是 WorkBuddy 官方资料来源。

## Practical interpretation

Claude Code 社区强调从 “vibe coding” 走向 “agentic engineering”：明确上下文、边界、子任务、验收和交付。办公 Agent 也需要类似升级：从“随口问一句”走向“可验收任务”和“可复用流程”。

核心迁移不是把代码仓库机制搬过来，而是迁移流程纪律：

```text
Research → Plan → Execute → Review → Ship
```

在 WorkBuddy 场景中可以理解为：调研输入和目标 → 制定任务计划 → 执行文件和办公流程 → 检查产物和变更 → 交付给同事或进入自动化。

## Methodology mapping

| Claude Code 侧重 | WorkBuddy 场景类比 | 必须注意 |
| --- | --- | --- |
| Commands | task templates / 固定 prompt / 企业场景 SOP；周期性任务才可能进入 Automation | WorkBuddy 没有完全等价的 `.claude/commands` 文件系统概念。 |
| Subagents / Agents | experts / expert teams | WorkBuddy 专家更偏产品化角色和方法论封装，不等于开发者完全文件化管理的 agent。 |
| Skills | WorkBuddy Skills | WorkBuddy Skill 更偏办公自动化、脚本和工作流封装，可涉及文件、API 或第三方服务。 |
| MCP | Connector 或 Cloud Agent 中的外部工具接入形态之一 | Connector 也可能是 Skill + CLI；不要把 MCP 与 Connector 直接画等号。 |
| CLAUDE.md / memory | 官方 Memory、任务历史、Expert 配置、Context Package 分别治理 | WorkBuddy Memory 是产品化记忆，不是项目内 Markdown 记忆文件。 |
| hooks | review gate / checklist / 人工确认点 | WorkBuddy 没有 Claude Code hooks 等价机制。 |
| permissions / sandbox | 默认权限、Full Access、工作空间、安全确认、沙箱策略 | 权限行为必须以 WorkBuddy 官方文档和产品界面为准。 |
| Review / Ship | 结果区的产物、全部文件、变更、预览 + 用户验收 checklist | 交付前必须验收，不因 Agent 已执行而默认正确。 |

## How to use this mapping

1. 看到重复办公任务时，先把它写成 task template，而不是立刻做 Automation。
2. 看到需要专业判断的步骤时，考虑设计 Expert 或专家团，而不是把所有要求塞进一个长 prompt。
3. 看到需要工具能力或外部系统时，评估 Skill / Connector，并先做安全审查。
4. 看到多次稳定执行后，再考虑 Automation。
5. 看到跨团队、版本、发布和生命周期管理需求时，再研究 Cloud Agent。

## Best practices

- 类比可以帮助理解，但事实必须回到 WorkBuddy 官方文档。
- 将 prompt 视为工程资产：命名、版本、适用范围、输入要求、验收标准都要记录。
- 为每个 workflow 配置 Reviewer 步骤：检查目标、输入、输出、文件、权限和风险。
- 在企业场景里，把“可执行”与“可审计”放在同等重要的位置。

## Common mistakes

- 把 Claude Code 的 `.claude/commands` 说成 WorkBuddy 官方目录机制。
- 把 Claude Code Subagent 等同于 WorkBuddy Expert。
- 把 MCP 连接器、Skill、CLI 工具混为一谈，不做边界说明。
- 只迁移术语，不迁移验收、权限和复盘纪律。

## Context Package Boundary

本仓库用 `docs/` 和 `templates/workbuddy-context/` 保存公开 Context Package 说明、prompt、workflow 和 review checklist。团队可以在私有项目中使用 `.workbuddy/` 做本地实验，但这不是 WorkBuddy 官方功能等价关系，也不能写成自动读取机制。

## Security / permission notes

Claude Code 和 WorkBuddy 都可能触及文件、命令、外部系统和自动化，但安全模型不同。任何跨产品类比都不能替代 WorkBuddy 官方权限说明、企业合规评估和本地测试。

## Template

```markdown
## Workflow Asset Card

- 名称：
- 来源：一次性任务 / 团队 SOP / Claude Code 方法论迁移
- WorkBuddy 实现方式：任务模板 / Expert / Skill / Connector / Automation / Cloud Agent
- 输入要求：
- 操作边界：
- 验收标准：
- 权限风险：
- 复盘记录：
```

## Further Reading

- [Claude Code best practice reference](https://github.com/shanraisshan/claude-code-best-practice)
- [WorkBuddy 官方简介](https://www.codebuddy.cn/docs/workbuddy/Overview)
- [WorkBuddy 专家](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Expert-Center)
- [WorkBuddy 技能](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market)
- [WorkBuddy 连接器](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector)
- [WorkBuddy 权限模式](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
- [WorkBuddy Context Convention](../docs/workbuddy-context-convention.md)
