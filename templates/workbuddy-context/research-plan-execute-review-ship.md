# Research, Plan, Execute, Review, Ship

适用场景：把一次仓库维护或企业办公 Agent 任务拆成可追踪、可验收的小步流程。  
风险等级：Medium。  
边界：这是方法论流程，不是 WorkBuddy 官方内置生命周期。

## Workflow

| Stage | What to do | Evidence |
|---|---|---|
| Research | 阅读官方文档、Changelog、当前 repo 文件和用户要求。 | 来源列表、受影响文件。 |
| Plan | 列出要改的文件、事实依据、风险边界和检查方式。 | Repair plan。 |
| Execute | 小步修改，不创建空文件，不提交临时产物。 | Git diff。 |
| Review | 检查事实、链接、标题、模板可复制性、安全边界和 `.workbuddy/` 表述。 | Review findings。 |
| Ship | 运行检查，提交 commit，写清 summary、checks、remaining limits。 | Checks output、commit。 |

## Guardrails

- WorkBuddy 官方事实只从官方文档和 Changelog 写入。
- Claude Code benchmark 只用于方法论和 repo 组织参考。
- `.workbuddy/` 只能作为本地实验或 repo convention 描述，不能写成官方目录规范。
- 发现同一错误两次后，先查官方文档或可靠来源，再选择最小有效修复。

## Further Reading

- [WorkBuddy Context Convention](../../docs/workbuddy-context-convention.md)
- [Result Review](../../01-getting-started/result-review.md)
- [Manual Run to Automation](../../03-workflows/manual-to-automation.md)
