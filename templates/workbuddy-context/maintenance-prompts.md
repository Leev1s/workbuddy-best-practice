# Maintenance Prompts

适用场景：维护公开 WorkBuddy best-practice 文档。  
风险等级：Medium。  
使用方式：复制一个 prompt，填入目标文件和官方来源，再让 Agent 执行。

## Create Best Practice Article

```markdown
请为 workbuddy-best-practice 新增或修改一篇文章。

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
- 不把 `.workbuddy/` 写成 WorkBuddy 官方目录规范。
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

## Extract Official Facts

```markdown
请阅读以下 WorkBuddy 官方文档页面：
- [URL 1]
- [URL 2]

请输出：

## Page Summary

- 页面：
- 主题：
- 核心官方事实：
- 适用场景：
- 边界与风险：
- 与本仓库哪些章节相关：

## Source Map

- 章节路径：
- 推荐 Further Reading：
- 可写入的官方事实：
- 不能写成官方事实的实践解释：

规则：
- 不复制大段原文。
- 不推断官方未说明的能力。
- 版本敏感内容先检查 Changelog。
```

## Safety Review

```markdown
请对以下文件做安全和事实边界审查：
- [文件路径]

检查项：
- 是否把 WorkBuddy 官方未说明的能力写成事实？
- 是否把 `.workbuddy/` 写成官方规范或自动读取目录？
- 是否把 Claude Code 的机制写成 WorkBuddy 官方机制？
- 是否涉及文件删除、覆盖、工作空间外写入、脚本执行、第三方外发？
- 是否说明默认权限、Full Access、工作空间或人工确认边界？
- 是否提醒 Skill / Connector / Automation / Memory / Cloud Agent 的数据和凭据风险？
- 是否包含 Further Reading 官方来源？

输出：
- Findings：按严重程度列出问题。
- Suggested edits：给出可直接替换的短文本。
- Pass criteria：哪些条件满足后可发布。
```

## Further Reading

- [Repository Maintenance Brief](repository-maintenance-brief.md)
- [Repository Review Checklist](repository-review-checklist.md)
