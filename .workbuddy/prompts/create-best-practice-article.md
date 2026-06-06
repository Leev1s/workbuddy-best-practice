# Prompt: Create Best Practice Article

用于让 WorkBuddy 或其他 Agent 在本仓库中新增一篇最佳实践文章。请先读取 `AGENTS.md`、`sources.md` 和目标目录 README，再写正文。

```markdown
请为 workbuddy-best-practice 新增/修改一篇文章。

主题：
- [填写主题]

目标目录：
- [例如 05-skills/]

必须使用的来源：
- WorkBuddy 官方文档：[列出 URL]
- sources.md 中对应条目

写作要求：
- 中文为主，保留必要 English 技术词。
- 区分 Official facts、Practical interpretation 和 Security / permission notes。
- 不复制官方文档大段原文。
- 不把 `.workbuddy/` 写成 WorkBuddy 官方规范。
- 不把 Claude Code 机制写成 WorkBuddy 官方能力。

默认结构：
- TL;DR
- Official facts
- Practical interpretation
- How to use
- Best practices
- Common mistakes
- Security / permission notes
- Further Reading

验收标准：
- 有实质内容，不使用占位符正文。
- Further Reading 包含官方来源。
- 内部链接使用相对路径。
```
