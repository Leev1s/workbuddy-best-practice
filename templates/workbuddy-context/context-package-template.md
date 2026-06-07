# Context Package Template

适用场景：需要让 WorkBuddy 或其他 Agent 在一个项目中稳定理解背景、术语、边界和验收标准。  
风险等级：Medium。  
注意：本模板不是 WorkBuddy 官方目录规范；使用时必须在 prompt 中显式引用。

```markdown
# Project Context

## Project Identity

- Project name:
- Owner:
- Audience:
- Business purpose:
- Official / internal source of truth:

## Task Scope

- In scope:
- Out of scope:
- Allowed input folders:
- Allowed output folders:
- Forbidden operations:

## Terminology

| Term | Meaning | Source |
|---|---|---|
| [term] | [definition] | [official / internal / practice] |

## Source Policy

- Official facts:
- Internal policy:
- Community / third-party observations:
- Version-sensitive pages to recheck:

## Security Rules

- Data classification:
- Files that must stay read-only:
- Operations requiring human confirmation:
- Skill / Connector / Automation restrictions:
- Sensitive data that must never be stored here:

## Review Checklist

- [ ] Output matches the requested format.
- [ ] Source claims are linked or labeled as practice interpretation.
- [ ] No sensitive data is included.
- [ ] Workspace-external writes, deletion, scripts, third-party calls, or Full Access are explicitly approved.
- [ ] Result files, changes, and previews have been checked.
```

## Further Reading

- [WorkBuddy Context Convention](../../docs/workbuddy-context-convention.md)
- [WorkBuddy 官方文档：创建任务](https://www.codebuddy.cn/docs/workbuddy/Create-Task)
- [WorkBuddy 官方文档：两个权限模式](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
