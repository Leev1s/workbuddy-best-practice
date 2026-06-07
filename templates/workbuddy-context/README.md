# WorkBuddy Context Templates

这些模板用于把项目上下文、维护规则、审查清单和可复用 prompt 组织成可复制的 Context Package。它们是本仓库实践资产，不是 WorkBuddy 官方目录规范。

| Template | Use it for | Risk level |
|---|---|---|
| [context-package-template.md](context-package-template.md) | 为项目准备可显式引用的背景、术语、规则和边界。 | Medium |
| [repository-maintenance-brief.md](repository-maintenance-brief.md) | 给 Agent 写一次仓库维护任务的完整 Task Brief。 | Medium |
| [repository-review-checklist.md](repository-review-checklist.md) | 发布前检查事实、结构、链接、安全和 `.workbuddy/` 边界。 | High |
| [maintenance-prompts.md](maintenance-prompts.md) | 复用官方事实抽取、文章创建、安全审查等 prompt。 | Medium |
| [research-plan-execute-review-ship.md](research-plan-execute-review-ship.md) | 把维护任务拆成 Research、Plan、Execute、Review、Ship。 | Medium |
| [markdown-asset-rules.md](markdown-asset-rules.md) | 统一 Markdown、图片和资产输出规则。 | Low |

## Usage

1. 复制需要的模板到你的项目文档、知识库或本地实验目录。
2. 在 WorkBuddy prompt 中显式引用文件路径和读取目的。
3. 删除示例字段，不保留占位符。
4. 不写入 API Key、Token、Cookie、客户资料、员工隐私或企业内部凭据。

## Further Reading

- [WorkBuddy Context Convention](../../docs/workbuddy-context-convention.md)
- [Task Brief Template](../task-brief-template.md)
- [Security Checklist](../security-checklist.md)
