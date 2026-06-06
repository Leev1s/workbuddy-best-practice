# Workflow: Update Changelog Watch

## Purpose

当 WorkBuddy 官方 Changelog 更新时，判断本仓库哪些章节需要修订。

## Steps

1. 打开 [WorkBuddy Changelog](https://www.codebuddy.cn/docs/workbuddy/Changelog)。
2. 记录最新版本号和发布日期。
3. 标记更新类型：任务、结果、权限、Skill、Connector、Automation、Memory、Model、Cloud Agent、Bug fix。
4. 对照 `sources.md` 的 source map 找到受影响章节。
5. 更新 `changelog-watch.md`，说明影响和建议动作。
6. 若涉及事实变化，更新对应文章的 Official facts 和 Further Reading。

## Rules

- 不把 Changelog 的 Bug fix 扩写成新能力。
- 版本敏感内容写明日期。
- 对安全、权限、自动化相关变化优先复查。
