# Prompt: Safety Review

用于审查本仓库中涉及权限、文件操作、Skill、Connector、Automation、Memory、Cloud Agent 的文章或模板。

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
