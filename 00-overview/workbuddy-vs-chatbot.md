# WorkBuddy vs Chatbot

## TL;DR

普通对话式 AI 通常擅长回答问题、提供建议和生成草稿。WorkBuddy 的使用重心是任务、工作空间、执行过程、产物、变更和预览。使用方式要从“问问题”转向“交代任务”，从“复制答案”转向“验收交付物”，从“单次对话”转向“可复用 workflow”。

## Official facts

- 官方简介将传统 AI 对话与 WorkBuddy 区分为：前者偏对话和建议，后者能够执行任务、操作本地文件、处理多步骤任务并交付可验收结果。
- 官方结果查看页面说明，WorkBuddy 的右侧结果区可查看产物、全部文件、变更和预览。

## Practical interpretation

Chatbot 的默认交付物是一段回答；WorkBuddy 的默认交付物应被理解为“任务结果包”：包含生成文件、修改内容、预览效果、执行过程中的假设和待确认事项。

这意味着用户要改变三件事：

1. **从问问题变成交代任务**：写清目标、输入、输出、约束和验收标准。
2. **从复制答案变成验收交付物**：检查文件、表格、PPT、网页或报告是否真的可交付。
3. **从单次对话变成可复用 workflow**：把跑通的做法沉淀为模板、清单、专家或自动化任务。

## Comparison table

| 维度 | 对话式 AI / Chatbot | WorkBuddy |
| --- | --- | --- |
| 主要形态 | 聊天窗口 | 任务 + 工作空间 + 结果区 |
| 典型输出 | 回答、建议、草稿 | 文件、报告、表格、PPT、变更、预览 |
| 用户输入 | 问题或指令 | 任务简报、上下文包、操作边界 |
| 执行方式 | 多数由用户手动复制和操作 | Agent 可拆解并执行多步骤任务 |
| 文件处理 | 通常需要用户手动上传、下载、复制 | 可在授权工作空间内读取和处理文件 |
| 验收方式 | 读回答是否满意 | 检查产物、全部文件、变更、预览 |
| 复用方式 | 保存 prompt | 模板、workflow、Expert、Skill、Connector、Automation |
| 主要风险 | 回答错误、幻觉 | 幻觉 + 文件误操作 + 权限 + 外部服务 + 自动化风险 |

## How to use

1. 先写“任务说明”，不要只写问题。
2. 把输入文件放入独立工作空间。
3. 要求 WorkBuddy 先列计划和风险点。
4. 让它按阶段执行：分析 → 产出 → 自检 → 交付。
5. 用结果区逐项验收。
6. 把本次任务抽象成可复用模板。

## Best practices

- 对复杂任务采用“先计划，后执行”。
- 对不确定任务采用“小样本试跑”，确认格式再批量处理。
- 对可交付产物，要求 WorkBuddy 同时给出“交付摘要”和“自检清单”。
- 对重复任务，先记录 prompt 和验收结果，再考虑 Automation。

## Common mistakes

- 把 WorkBuddy 当 Chatbot，只写一句模糊需求。
- 只看对话区结论，不看右侧结果区。
- 让 WorkBuddy 直接处理原始目录，没有准备工作空间。
- 没有检查外部调用、文件写入和删除操作。

## Security / permission notes

WorkBuddy 的价值来自执行能力，风险也来自执行能力。越接近文件修改、批量操作、脚本执行、外部 API、无人值守自动化，越要强化权限边界、备份和人工验收。

## Template

```markdown
请按任务方式处理，而不是只给建议：
1. 先复述任务理解。
2. 列出需要的输入和缺失信息。
3. 给出执行计划和风险点。
4. 等我确认后再处理文件。
5. 完成后列出产物、修改文件、未确认假设和验收建议。
```

## Further Reading

- [WorkBuddy 官方简介](https://www.codebuddy.cn/docs/workbuddy/Overview)
- [WorkBuddy 结果查看](https://www.codebuddy.cn/docs/workbuddy/Results)
- [WorkBuddy 是什么](what-is-workbuddy.md)
- [WorkBuddy 任务 Prompt 模板](../01-getting-started/task-prompt-template.md)
