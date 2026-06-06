# WorkBuddy 是什么

## TL;DR

WorkBuddy 是腾讯推出的全场景职场 AI 智能体桌面工作台，面向办公任务而不是单纯问答。普通 Chatbot 更偏“回答”，WorkBuddy 更偏“执行”：它可以围绕工作空间处理文件、拆解步骤、生成交付物，并通过结果区让用户验收。它适合文档、数据、PPT、研究、批量文件、邮件、周报和会议纪要等场景，但仍需要人类明确任务边界并验收结果。

## Official facts

- 官方简介将 WorkBuddy 定位为“全场景职场 AI 智能体桌面工作台”，面向各类职能角色，用自然语言描述需求后由 WorkBuddy 规划和执行任务，并交付可验收结果。
- 官方简介列出的核心能力包括自然语言理解、自主规划执行、多模态任务处理和本地文件操作。
- 官方简介列出的适用场景包括文档生成、数据分析、PPT / 报告生成、深度研究、邮件编辑、周报生成和批量文件处理。
- 官方结果查看页面说明，结果区包含产物、全部文件、变更和预览，用于检查任务交付内容。

## Practical interpretation

把 WorkBuddy 当作“能处理办公文件和多步骤流程的执行型 Agent”，而不是只会聊天的助手。更好的使用方式是：

1. 给它明确目标，而不是只给主题。
2. 给它输入文件、背景资料和规则，而不是让它猜。
3. 给它输出格式、保存位置和操作边界。
4. 用结果区检查产物和变更，而不是只读最后一段回复。

## How to use

1. 先把模糊需求写成 Task Brief：目标、输入、输出、约束、验收标准。
2. 建立独立工作空间，只放本次任务需要处理的文件副本。
3. 如果任务会长期复用，可在项目中维护 `.workbuddy/` 存放背景、规则、术语表、prompt、workflow 和验收清单，并在 prompt 中显式引用；这只是本仓库实践约定，不是 WorkBuddy 官方规范。
3. 发起任务并要求 WorkBuddy 先复述理解、列计划。
4. 对涉及文件修改、脚本、外部服务的步骤保持确认。
5. 在交付前检查产物、全部文件、变更和预览。
6. 将成功流程沉淀为模板或 Automation 候选。

## Best practices

- 每个任务都写清楚“什么算完成”。
- 重要资料先复制到独立目录，不直接处理唯一副本。
- 对数据分析、财务、合同、客户资料等任务，要求列出假设和未确认点。
- 批量文件处理前先生成清单，再执行重命名、移动或删除。
- 把稳定流程沉淀到 [任务简报模板](../templates/task-brief-template.md) 和 [验收清单](../templates/review-checklist.md)。

## Common mistakes

- 只写“帮我做个报告”，没有目标、受众、数据来源和格式要求。
- 把生成的文本直接复制交付，没有核对输入覆盖率和事实准确性。
- 把第三方 Skill / Connector 当成默认可信能力。
- 一开始就做 Automation，没有先手动跑通和验收。
- 认为 Agent 执行了就等于结果正确。

## Security / permission notes

- WorkBuddy 能处理本地文件，因此任务理解偏差可能造成写错目录、覆盖文件或误删文件。
- 第三方 Skill / Connector 可能涉及数据外发、API 调用或脚本执行，使用前需要评估来源、权限和数据流。
- Automation 带来无人值守风险：任务一旦定时运行，错误可能重复发生。
- 模型输出仍可能存在幻觉、遗漏和格式错误，必须有人类验收。

## Template

```markdown
请先不要直接执行，先复述你的任务理解并列出计划。

目标：
输入：
输出：
工作空间：
允许操作：
禁止操作：
验收标准：
风险提醒：
```

## Further Reading

- [WorkBuddy 官方简介](https://www.codebuddy.cn/docs/workbuddy/Overview)
- [WorkBuddy 结果查看](https://www.codebuddy.cn/docs/workbuddy/Results)
- [WorkBuddy 权限模式](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
- [WorkBuddy vs Chatbot](workbuddy-vs-chatbot.md)
- [办公 Agent 工程化心智模型](mental-model.md)
