# WorkBuddy 任务 Prompt 模板

## TL;DR

WorkBuddy 任务 prompt 应该像任务简报，而不是聊天问题。坏 prompt 是“帮我做个报告”；好 prompt 会说明目标、输入、输出格式、约束条件、操作边界、验收标准和风险提醒。写得越像可验收任务，越容易得到可交付结果。

## Official facts

- WorkBuddy 官方简介强调用户可以用自然语言描述需求，WorkBuddy 进行规划和执行。
- 官方结果查看页面提供产物、全部文件、变更和预览，说明任务输出应被用户检查和验收。
- 官方权限模式页面说明，涉及工作空间外写入、删除文件、执行脚本、调用敏感能力等操作时需要关注权限和确认。

## Bad prompt

```text
帮我做个报告。
```

问题：

- 没有说明报告主题、读者、目的。
- 没有说明输入数据或资料来源。
- 没有说明输出格式和保存位置。
- 没有说明能不能修改文件、调用工具或联网。
- 没有验收标准，无法判断是否完成。

## Good prompt template

```markdown
请先复述你的任务理解并列出执行计划，等我确认后再正式处理文件。

## 目标

[说明这次任务要达成什么业务结果]

## 输入

- 文件 / 文件夹：
- 背景资料：
- 参考样例：
- 必须使用 / 不得使用的数据来源：
- 项目级上下文文档（可选）：例如 `docs/`、`templates/workbuddy-context/` 或团队私有知识库；请说明要读取哪些文件。

## 输出格式

- 输出文件类型：
- 文件命名规则：
- 保存位置：
- 结构要求：

## 约束条件

- 语言 / 字数 / 页数：
- 风格 / 受众：
- 数据口径：
- 时间范围：

## 操作边界

允许：
- [允许读取哪些目录]
- [项目级上下文文档是否只读；默认建议只读，除非任务明确要求修改]
- [允许新建哪些文件]

禁止：
- [禁止删除 / 覆盖哪些文件]
- [禁止调用哪些外部服务]
- [禁止处理哪些敏感数据]

## 验收标准

- [可检查条件 1]
- [可检查条件 2]
- [可检查条件 3]

## 风险提醒

- 如果缺少信息，请先提问，不要自行编造。
- 如果需要删除、覆盖、执行脚本或外部调用，请先说明并等待确认。
- 完成后请列出产物、修改文件、未确认假设和建议检查项。
```

## Example 1: Excel 数据分析

```markdown
请分析工作空间中的 `sales_2026_q1.xlsx`，先复述任务理解并列出计划。

目标：找出 Q1 销售额变化、Top 10 客户、异常波动月份，并给出管理层摘要。
输入：只使用 `sales_2026_q1.xlsx`，不要使用外部数据。
输出：
- `output/q1_sales_analysis.md`：分析报告，包含结论、图表说明、异常点和建议。
- `output/q1_sales_summary.csv`：按月份、区域、产品汇总的数据表。
约束：所有金额保留两位小数；如果字段含义不明确，先列出假设。
操作边界：允许读取工作空间内 Excel；允许在 `output/` 新建文件；禁止修改原始 Excel。
验收标准：结论必须能追溯到输入字段；报告包含至少 3 条业务洞察；列出数据质量问题。
风险提醒：不要编造缺失字段；不要覆盖原文件。
```

## Example 2: 会议纪要转 PPT

```markdown
请把 `meeting-notes.md` 转成给部门例会使用的 PPT 大纲和演示稿草案。

目标：让未参会同事在 10 分钟内理解会议结论、待办和风险。
输入：`meeting-notes.md`，如有不清楚的负责人或截止时间，请标为“待确认”。
输出：
- `output/meeting-briefing-outline.md`：PPT 逐页大纲。
- 如支持生成 PPT，请输出到 `output/meeting-briefing.pptx`；否则只生成 Markdown 大纲。
约束：不超过 8 页；每页标题不超过 18 个汉字；保留关键决策和 Action Items。
操作边界：禁止删除或改写原会议纪要。
验收标准：包含背景、关键结论、行动项、风险、下一步；行动项有负责人和截止时间或标注待确认。
风险提醒：不要把未确认事项写成已确定结论。
```

## Example 3: 文件批量整理

```markdown
请整理工作空间 `inbox/` 中的文件，但先只生成整理方案和文件清单，不要移动、删除或重命名。

目标：把文件按合同、发票、会议、图片、其他进行分类，形成可复核清单。
输入：仅限 `inbox/` 目录。
输出：
- `output/file_inventory.csv`：原路径、建议分类、建议新文件名、理由、风险等级。
- `output/rename_plan.md`：整理规则和需要人工确认的文件。
约束：无法判断类别时标为“待确认”；不要根据猜测删除文件。
操作边界：当前阶段禁止移动、删除、重命名；只允许读取和生成清单。
验收标准：所有文件都出现在清单中；高风险文件单独列出；下一步执行命令需等待我确认。
风险提醒：批量整理容易误删或覆盖，执行前必须二次确认。
```

## Best practices

- 对复杂任务先要求 WorkBuddy 复述理解并列计划。
- 对批量任务采用“两阶段”：先清单，后执行。
- 对涉及外部服务的任务，明确是否允许外发数据。
- 对交付文档，明确受众、语气、结构和长度。
- 对数据任务，明确字段口径、时间范围和缺失值处理方式。

## Common mistakes

- 输入文件名不准确，导致 Agent 使用错误文件。
- 没有指定输出目录，产物散落在工作空间中。
- 允许范围写得太宽，导致不必要的文件访问。
- 没有定义“完成”，只能凭主观感觉验收。

## Security / permission notes

在 prompt 中明确 Allowed Operations 和 Forbidden Operations。尤其是删除、覆盖、批量重命名、执行脚本、联网、调用第三方服务、处理敏感数据，都应先说明并等待确认。

## Template

使用完整模板请复制：[WorkBuddy Task Brief Template](../templates/task-brief-template.md)。

## Further Reading

- [WorkBuddy 官方简介](https://www.codebuddy.cn/docs/workbuddy/Overview)
- [WorkBuddy 创建任务](https://www.codebuddy.cn/docs/workbuddy/Create-Task)
- [WorkBuddy 结果查看](https://www.codebuddy.cn/docs/workbuddy/Results)
- [WorkBuddy 权限模式](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
- [WorkBuddy Result Review Checklist](../templates/review-checklist.md)
- [WorkBuddy Context Convention](../docs/workbuddy-context-convention.md)
