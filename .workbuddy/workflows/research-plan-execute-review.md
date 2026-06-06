# Research → Plan → Execute → Review Workflow

## Purpose

用于维护本知识库时，把用户需求从“写一篇 / 改一下”转换为可追踪、可验收的小步变更。

## Steps

1. **Research**：阅读 `AGENTS.md`、`README.md`、`.workbuddy/` 稳定上下文和相关章节；涉及新功能时检查官方 Changelog。
2. **Plan**：列出要改的文件、来源依据、风险边界和测试方式。
3. **Execute**：小步修改，不创建大量空文件，不提交临时产物。
4. **Review**：检查标题层级、相对链接、Further Reading、安全说明和 `.workbuddy/` 边界表述。
5. **Ship**：运行检查，提交 commit，写清 summary 与 testing。

## Guardrails

- `.workbuddy/` 是项目级上下文目录，不是 WorkBuddy 官方 Memory 或自动加载机制。
- 对第三方资料只写“社区观察 / 第三方评价”。
- 对高风险能力优先写安全规范、验收清单和人工确认点。

## Further Reading

- [Mental Model](../../00-overview/mental-model.md)
- [Result Review](../../01-getting-started/result-review.md)
