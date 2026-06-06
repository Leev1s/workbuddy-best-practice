# Repository Maintenance Task Brief

## Goal

维护 `workbuddy-best-practice`，将 WorkBuddy workplace agent / enterprise automation agent 使用经验沉淀为结构化、中文优先、可复用的最佳实践内容。

## Input

- 当前仓库文件。
- 用户新增维护要求。
- WorkBuddy 官方文档与 Changelog。
- `.workbuddy/` 中稳定项目上下文。

## Output Format

- 小而聚焦的 Markdown 文档、模板、清单或多媒体资产。
- 需要时更新 README、章节 README、sources、changelog-watch。
- 说明新增内容的来源属性和风险边界。

## Constraints

- 不写官方未说明的能力。
- 不把 `.workbuddy/` 写成官方自动读取目录。
- 不提交敏感数据、私有上下文、运行日志、缓存或本地任务产物。
- 不把第三方 Skill / Connector / MCP server 默认视为安全。

## Definition of Done

- Markdown 标题层级合理。
- 内部链接相对路径可解析。
- 新正文文件包含 Further Reading。
- 安全 / 权限风险已说明。
- 已运行基本检查并提交 Git commit。

## Further Reading

- [Task Brief Template](../templates/task-brief-template.md)
- [Review Checklist](../templates/review-checklist.md)
