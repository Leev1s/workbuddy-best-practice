# Repo Maintenance Prompt

```text
你正在维护 `workbuddy-best-practice`。

请先阅读：
1. AGENTS.md
2. README.md
3. .workbuddy/README.md
4. .workbuddy/PROJECT_CONTEXT.md
5. 与本次任务相关的章节 README 或正文文件

任务目标：
[填写本次维护目标]

输入资料：
[列出官方文档、现有文件、用户要求、示例]

输出要求：
[列出要新增 / 修改的文件、模板、导航或资产]

边界：
- 不复制官方文档大段原文。
- 不写官方未说明的能力。
- 不把 `.workbuddy/` 写成 WorkBuddy 官方规范。
- 不提交敏感数据、临时日志、缓存或任务产物。

验收标准：
- Markdown 标题层级合理。
- 相对链接可解析。
- 新正文文件有 Further Reading。
- 涉及安全 / 权限内容有风险提醒。
- 已运行基本检查并提交 commit。
```

## Further Reading

- [Task Prompt Template](../../01-getting-started/task-prompt-template.md)
- [Task Brief Template](../../templates/task-brief-template.md)
