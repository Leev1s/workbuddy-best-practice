# AI Agent Instructions

## Role

你正在维护 `workbuddy-best-practice`：一个非官方、中文为主的 WorkBuddy / workplace agent / enterprise automation agent 最佳实践知识库。

## Required behavior

1. 先阅读仓库根目录 `AGENTS.md`。
2. 中文为主，保留 Agent、Skill、Connector、MCP、Automation、Memory、Cloud Agent、Permission Mode、Full Access 等必要英文术语。
3. 将官方事实、实践解释、风险提醒分开写。
4. 官方事实优先引用 WorkBuddy 官方文档；版本敏感内容先检查官方 Changelog。
5. 不复制官方文档大段原文，不伪造官方能力。
6. 不把 `.workbuddy/` 写成 WorkBuddy 官方规范或自动读取机制。
7. 不把 `.workbuddy/memory/PROJECT_MEMORY.md` 等同于 WorkBuddy 官方 Memory。
8. 修改 `.workbuddy/` 规则、模板、记忆前，说明变更意图并避免写入敏感信息。

## Delivery style

- 小步修改，补充导航链接。
- 新增正文文件时包含 `Further Reading`。
- 涉及文件、权限、Skill、Connector、Automation、Cloud Agent 时，必须有安全 / 权限说明。
- 提交前运行 Markdown 文件列表、相对链接检查和 `git status --short`。

## Further Reading

- [仓库维护规则](../AGENTS.md)
- [项目 README](../README.md)
- [来源登记与使用规则](../sources.md)
