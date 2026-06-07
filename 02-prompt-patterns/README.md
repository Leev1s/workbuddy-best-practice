# Prompt Patterns for WorkBuddy Tasks

## TL;DR

好的 WorkBuddy prompt 不是把一句话写长，而是把任务变成可执行、可验收、可追责的 Task Brief。默认结构是：目标、输入、工作目录、上下文、输出格式、权限边界、验收标准。

## Official facts

WorkBuddy 官方文档说明，创建任务时可以用自然语言描述需求，也可以选择工作目录，并通过 `@` 引用上下文、上传文件、粘贴截图或补充说明来帮助 WorkBuddy 理解目标、范围、约束和预期输出。

官方结果查看文档说明，任务执行过程中可以在结果区查看产物、全部文件、变更和预览；这意味着 prompt 中应提前定义结果如何验收，而不是只要求“帮我做好”。

## Practical interpretation

办公 Agent prompt 的重点不是“更会聊天”，而是减少误解和返工：

- 目标说明让 Agent 知道最终交付物是什么。
- 输入说明让 Agent 知道哪些文件、数据、截图可以用。
- 边界说明让 Agent 知道哪些目录、系统、账号、动作不能碰。
- 验收标准让用户知道什么时候可以接受结果。

## Core pattern

```markdown
请完成以下任务：

目标：
- [说明要完成什么，不要只写“优化一下”]

输入材料：
- [文件/截图/链接/表格/会议纪要]

工作目录：
- [指定目录；如无，请说明让 WorkBuddy 在默认目录生成结果]

上下文：
- [业务背景、术语、风格、受众、必须遵守的规则]

输出：
- [文件类型、命名、章节结构、表格字段、语言]

限制：
- [不要删除文件；不要写工作空间外路径；不要调用第三方服务；不要编造数据]

验收标准：
- [检查项 1]
- [检查项 2]
- [检查项 3]
```

## Best practices

- 把“请帮我做”改成“请交付什么文件，并满足哪些检查项”。
- 首次运行复杂任务时，要求 WorkBuddy 先列计划，再执行。
- 涉及文件批量处理时，要求先输出待处理清单和备份策略。
- 涉及外部系统、Skill、Connector 或 Automation 时，先写明授权范围和停止条件。
- 对报告、PPT、表格类任务，提前给出结构、字段、受众和语气。

## Common mistakes

- 只描述动作，不描述交付物。
- 只上传文件，不说明哪些文件可改、哪些只读。
- 把“自动化”写成无人监管，缺少失败处理和人工确认节点。
- 让 Agent 自行决定事实来源，导致把未核验内容写成事实。
- 没有验收标准，结果区只能凭感觉检查。

## Security / permission notes

涉及删除、覆盖、批量重命名、执行脚本、访问第三方服务或写入工作空间外路径时，应要求 WorkBuddy 先解释计划并等待确认。默认权限不是备份系统，重要资料仍应先复制到独立工作空间。

## Template or checklist

- [Task Brief Template](../templates/task-brief-template.md)
- [Review Checklist](../templates/review-checklist.md)
- [Security Checklist](../templates/security-checklist.md)
- [Task Brief Patterns](task-brief-patterns.md)

## Further Reading

- [WorkBuddy Create Task](https://www.codebuddy.cn/docs/workbuddy/Create-Task)
- [WorkBuddy Task Chat](https://www.codebuddy.cn/docs/workbuddy/Task-Chat)
- [WorkBuddy Results](https://www.codebuddy.cn/docs/workbuddy/Results)
- [WorkBuddy Permission Modes](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
- [Task Brief Patterns](task-brief-patterns.md)
