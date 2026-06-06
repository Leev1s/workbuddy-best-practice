# Prompt: Extract Official Facts

用于从 WorkBuddy 官方文档中抽取事实索引。输出应短、结构化，不写成长篇教程。

```markdown
请阅读以下 WorkBuddy 官方文档页面：
- [URL 1]
- [URL 2]

请输出：

## Page summary
- 页面：
- 主题：
- 核心官方事实：
- 适用场景：
- 边界与风险：
- 与本仓库哪些章节相关：

## Source map
- 章节路径：
- 推荐 Further Reading：
- 可写入的官方事实：
- 不能写成官方事实的实践解释：

规则：
- 不复制大段原文。
- 不推断官方未说明的能力。
- 版本敏感内容先检查 Changelog。
```
