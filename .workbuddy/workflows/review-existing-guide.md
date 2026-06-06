# Workflow: Review Existing Guide

## Purpose

审查已有文章是否符合 v0.1 的公开发布标准。

## Checklist

- 标题层级是否清楚。
- 是否包含 TL;DR。
- 是否区分官方事实和实践解释。
- 是否包含 Further Reading。
- 是否存在只写占位符或空段落的正文。
- 是否有过度营销或夸大产品能力。
- 是否把 `.workbuddy/` 写成官方规范。
- 是否把 Claude Code 机制映射为 WorkBuddy 官方能力。
- 是否覆盖权限、安全或数据风险。
- 内部链接是否能解析。

## Suggested command checks

```bash
find . -name "*.md" -type f | sort
find . -name "*.md" -type f -empty
grep -R "[占位符关键词]" -n . --include="*.md" || true
grep -R "[错误官方规范表述]" -n . --include="*.md" || true
grep -R "[错误官方目录表述]" -n . --include="*.md" || true
git status --short
```
