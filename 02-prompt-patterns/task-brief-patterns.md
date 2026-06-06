# Task Brief Patterns

## TL;DR

Task Brief 是 WorkBuddy 任务的最小可复用单元。它把一句自然语言需求拆成“目标、输入、上下文、输出、权限、验收”，适合文档生成、数据分析、批量文件处理、调研和自动化前置验证。

## Official facts

官方创建任务文档说明，用户可以用一句话描述任务、选择工作目录、通过 `@` 引用上下文、上传文件、粘贴截图，并补充目标、输入、约束和预期输出。

官方结果查看文档说明，WorkBuddy 提供产物、全部文件、变更和预览等视图，方便用户在接受结果前检查文件内容和修改范围。

## Practical interpretation

Task Brief 的价值在于把“你觉得它应该懂”的信息显式写出来。WorkBuddy 可以自主规划和执行，但企业任务通常需要可审查的范围、数据来源和验收标准。

## How to use

### Pattern 1: 文档生成

```markdown
目标：根据输入材料生成一份 [受众] 可读的 [文档类型]。
输入：@[文件名]，仅作为事实来源。
结构：背景、关键发现、建议、风险、下一步。
输出：生成 Markdown 和 Word 友好的标题层级；不要编造未出现的数据。
验收：事实均可回溯到输入；摘要不超过 300 字；风险单独列出。
```

### Pattern 2: 数据分析

```markdown
目标：分析 @[数据文件] 并输出可复核的分析报告。
限制：不要改变原始数据文件；如需清洗，请生成副本。
输出：数据概览、清洗说明、核心指标、图表建议、异常值说明。
验收：说明使用的字段；列出缺失值和异常值处理方式；图表结论不夸大。
```

### Pattern 3: 批量文件处理

```markdown
目标：整理工作目录中的 [文件类型]。
执行前：先列出将被移动/重命名/修改的文件清单，并等待确认。
限制：不要删除原文件；不要处理工作空间外文件。
输出：整理后的目录结构和处理日志。
验收：文件数量前后一致；命名规则一致；可回滚。
```

### Pattern 4: 自动化设计

```markdown
目标：把已验证的人工流程整理成 Automation 任务草案。
触发条件：[一次性/周期性/事件]
输入来源：[文件/连接器/资料库/人工补充]
停止条件：[缺少数据/权限失败/结果异常]
人工确认：[哪些步骤必须确认后才能继续]
输出：自动化任务说明、风险边界、失败处理。
```

## Best practices

- 每个 Task Brief 只交付一种主产物。
- 对“事实来源”使用白名单，不让 Agent 自由混入未核验资料。
- 把“不要做什么”写进限制区，例如不要删除、不要覆盖、不要外发。
- 对长任务先要求计划和文件清单，再允许执行。
- 把成功的 Task Brief 移入 `templates/` 或 `.workbuddy/prompts/`。

## Common mistakes

- 把复杂项目塞进一个 prompt，导致计划、写作、执行和验收混在一起。
- 不写工作目录，结果生成在默认目录后难以追踪。
- 不说明输入文件是否可修改。
- 对数据分析只要求结论，不要求字段、口径和异常说明。

## Security / permission notes

默认建议把源文件视为只读。需要批量改名、移动、覆盖或删除时，先生成清单和备份方案；需要 Full Access 时，优先在隔离目录、虚拟机或临时环境中测试。

## Further Reading

- [WorkBuddy Create Task](https://www.codebuddy.cn/docs/workbuddy/Create-Task)
- [WorkBuddy Results](https://www.codebuddy.cn/docs/workbuddy/Results)
- [WorkBuddy Permission Modes](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
- [Task Brief Template](../templates/task-brief-template.md)
