# Sources

This file records long-term reference sources for `workbuddy-best-practice`. It is a source map, not a copy of external documentation.

## Source Usage Rules

- WorkBuddy 官方文档是功能事实的优先来源。
- WorkBuddy 官方 Changelog 是版本敏感内容的优先来源。
- 第三方文章只能作为社区观察、案例线索或方法论参考，不能作为官方能力证明。
- 不复制官方文档大段原文；正文应以自己的话总结，并链接到来源。
- 如果官方文档没有明确说明某项能力，应写成实践建议、类比或假设，或者不写。
- 不把 Claude Code 的 agents、skills、commands、MCP 使用方式写成 WorkBuddy 官方机制。
- 公开 repo 不默认创建 `.workbuddy/`；如团队本地使用，应标为 experimental / repository convention。

## Official WorkBuddy Docs

### WorkBuddy 简介

- URL: <https://www.codebuddy.cn/docs/workbuddy/Overview>
- Type: official
- Core facts:
  - WorkBuddy 被官方描述为全场景职场 AI 智能体桌面工作台。
  - 核心能力包括自然语言任务、自主规划执行、多模态任务处理、本地文件操作和可验收结果。
  - 官方将 WorkBuddy 与传统 AI 对话区分为：不仅回复建议，也能执行多步骤任务并交付文件或结果。
- Use for:
  - `00-overview/`
  - `01-getting-started/`
  - README positioning
- Boundaries:
  - 只能说明官方列出的通用能力，不要扩展为“适用于所有企业系统”或“可替代人工审核”。

### 快速开始

- URL: <https://www.codebuddy.cn/docs/workbuddy/Quickstart>
- Type: official
- Core facts:
  - 官方列出 WorkBuddy 的产品概述、环境要求、进入方式和界面区域。
  - 快速开始页面说明侧边栏、对话区、结果区等基础界面概念。
  - 适用场景覆盖日常办公、代码开发、设计创意等模式。
- Use for:
  - `01-getting-started/`
  - onboarding checklist
  - first-task guides
- Boundaries:
  - UI 文案和入口可能随版本变动；写操作步骤前应复查 Changelog。

### 创建任务

- URL: <https://www.codebuddy.cn/docs/workbuddy/Create-Task>
- Type: official
- Core facts:
  - WorkBuddy 支持用自然语言描述任务。
  - 创建任务时可选择工作目录；WorkBuddy 会基于指定目录读取和处理文件，或在默认目录生成结果。
  - 可通过 `@` 引用上下文、粘贴截图、上传文件、补充目标/范围/约束/预期输出等方式增加上下文。
- Use for:
  - `01-getting-started/task-prompt-template.md`
  - `02-prompt-patterns/`
  - `03-workflows/`
  - task brief templates
- Boundaries:
  - 不要把“一句话描述任务”理解成无需边界、验收标准或上下文准备。

### 任务管理

- URL: <https://www.codebuddy.cn/docs/workbuddy/Task-Management>
- Type: official
- Core facts:
  - 侧边栏展示任务和工作空间；可查看、继续处理和切换上下文。
  - 常见状态包括进行中、已完成、失败、待处理、规划中、已归档。
  - 已完成、失败或中断的任务可以继续补充消息，在已有上下文基础上推进。
  - 任务可置顶、打开文件夹、重命名、保存到工作空间、删除或归档。
- Use for:
  - `01-getting-started/result-review.md`
  - `03-workflows/`
  - changelog impact notes
- Boundaries:
  - 不要发明官方未列出的任务状态或生命周期。

### 任务对话

- URL: <https://www.codebuddy.cn/docs/workbuddy/Task-Chat>
- Type: official
- Core facts:
  - Use as the primary official page for continuing instructions, file/context interaction, and multi-turn task refinement.
- Use for:
  - `02-prompt-patterns/`
  - `03-workflows/`
  - result iteration guidance
- Research note:
  - 2026-06-06 抓取该页面时网页工具返回 cache miss；后续写正文前应重新打开确认细节。
- Boundaries:
  - 不要凭经验补写页面未核实的具体按钮、快捷键或状态。

### 结果查看

- URL: <https://www.codebuddy.cn/docs/workbuddy/Results>
- Type: official
- Core facts:
  - 右侧结果区用于查看产物、全部文件、变更和预览。
  - 产物区可查看文档、表格、PPT、分析报告等交付文件。
  - 预览适合查看网页、页面原型或本地 Web 应用。
  - 全部文件用于查看工作空间中文件内容；变更用于检查本次任务带来的文件修改。
- Use for:
  - `01-getting-started/result-review.md`
  - `03-workflows/`
  - templates/review checklist
- Boundaries:
  - “可验收”应写成需要用户检查产物、文件、变更和预览，而不是默认结果正确。

### 更新日志

- URL: <https://www.codebuddy.cn/docs/workbuddy/Changelog>
- Type: official
- Core facts:
  - 2026-06-03 的 4.24.8 版本修复上下文压缩、历史会话加载、任务停止、Windows 沙箱日志和沙箱命令重试弹窗相关问题。
  - 2026-06-01 的 4.24.7 版本修复自动化定时任务重复触发问题。
  - 2026-06-01 的 4.24.6 版本涉及 content filter 展示、MCP 工具注入、自动化技能下拉、集成指南链接等修复。
  - 4.24.0 到 4.24.3 包含权限模式入口、完全放开确认、专家、连接器、Skill、自动化、沙箱和任务状态等多个影响最佳实践的变更。
- Use for:
  - `changelog-watch.md`
  - all version-sensitive claims
- Boundaries:
  - 不把修复项写成“风险已彻底消除”；仍需保留备份、验收和审计建议。

### 高效使用小技巧

- URL: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Efficient-Tips>
- Type: official
- Core facts:
  - 官方建议清晰表达任务、拆分大任务、多轮调整、先本地桌面端试用再考虑远程/自动化、善用专家和参考样本。
  - 官方提醒处理真实文件前应备份，自动化适合重复性高、规则明确、无需实时人工干预的任务。
- Use for:
  - `02-prompt-patterns/`
  - `03-workflows/`
  - `templates/task-brief-template.md`
  - `templates/review-checklist.md`
- Boundaries:
  - 可转化为方法论，但不要复制示例正文。

## Official Capability Docs

### 专家 / 专家团

- URL: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Expert-Center>
- Type: official
- Core facts:
  - 专家用于为 WorkBuddy 配置专业角色。
  - 专家中心和我的专家支持浏览、召唤和创建专家；专家团由多位专家分工协作，由团长拆解、并行执行和整合交付。
  - 官方说明专家本身不主动获取系统权限；配备 Skill / MCP 时才可能在授权下间接访问文件或外部服务。
  - 专家团可能带来更高积分消耗；专业领域输出不构成医疗、法律、投资、合规等正式专业意见。
- Use for:
  - `04-experts/`
  - expert card template
  - case studies involving domain roles
- Boundaries:
  - 不要把 WorkBuddy 专家团等同于 Claude Code subagents；只能作为“多角色协作方法论”类比。

### 技能 Skill

- URL: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market>
- Type: official
- Core facts:
  - Skill 为 WorkBuddy 增加特定工具能力，封装脚本与工作流，使 AI 在用户授权下完成具体动作。
  - 官方页面说明技能市场、已安装、本地技能包导入、查找技能、创建技能、启用/关闭、搜索和卸载。
  - Skill 可能涉及账户身份、联系方式、输入内容、日志、第三方平台凭证、本地文件读写、屏幕与输入控制权限等数据。
  - 官方建议优先使用官方推荐 Skill；安装第三方 Skill 前审查来源、权限申请和脚本内容。
- Use for:
  - `05-skills/`
  - `templates/skill-evaluation-template.md`
  - `08-permission-security/`
- Boundaries:
  - 第三方 Skill 默认不可信；不能把市场可安装写成安全审计通过。

### 连接器 Connector

- URL: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector>
- Type: official
- Core facts:
  - Connector 用于将 WorkBuddy 与外部服务对接，实现数据互通与能力扩展。
  - 技术形态包括 MCP + CLI 和 Skill + CLI。
  - 官方列举 QQ 邮箱、腾讯文档、腾讯乐享、腾讯会议、TAPD 等连接器，并支持自定义连接器。
  - 每个连接器独立授权；授权后可禁用或断开；外部数据理解和汇总可能产生积分消耗。
  - Connector 涉及第三方账号标识、授权凭据、第三方业务数据和用户写入数据。
- Use for:
  - `06-connectors/`
  - `templates/connector-evaluation-template.md`
  - `08-permission-security/`
  - workflow and case-study articles involving external systems
- Boundaries:
  - 不要承诺 Connector 不会访问敏感数据；应按已授权范围和第三方协议评估。

### 自动化 Automation

- URL: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide>
- Type: official
- Core facts:
  - Automation 让 WorkBuddy 按设定时间执行周期性、重复性任务，并将结果保存到指定目录。
  - 自动化配置保存在本地客户端，包括任务名称、prompt、调度规则、工作目录、执行状态等。
  - 触发时以当前登录身份发起 Agent 任务；可指定模型和技能、设置定时规则，并可推送到 WorkBuddy 小程序。
  - 官方提醒无人值守任务涉及文件写入/删除/资金操作时需审慎；建议低频试运行后再放大频率。
- Use for:
  - `07-automation/`
  - `templates/automation-template.md`
  - `templates/security-checklist.md`
  - case studies for recurring reports
- Boundaries:
  - 自动化不等于免审计；涉及对外发送、删除、批量写入、第三方调用时必须设计日志、预演和回滚。

### 权限模式 Permission Modes

- URL: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes>
- Type: official
- Core facts:
  - WorkBuddy 提供默认权限和 Full Access / 完全放开两种权限模式。
  - 工作空间是当前任务主要读取和保存文件的文件夹。
  - 默认权限下，写入或修改工作空间外文件、删除文件或目录、执行脚本/命令/外部程序、调用敏感能力等高风险动作会要求二次确认。
  - Full Access 会关闭上述二次确认；官方建议仅在可信、隔离、可恢复的环境中短时间使用。
- Use for:
  - `08-permission-security/`
  - `templates/security-checklist.md`
  - `templates/workbuddy-context/repository-review-checklist.md`
  - any article involving file operations or scripts
- Boundaries:
  - 默认权限不是备份机制；Full Access 不应作为日常默认模式。

### 记忆 Memory

- URL: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Memory>
- Type: official
- Core facts:
  - Memory 从会话历史中提取具有参考价值的个人信息、偏好习惯、人物关系、近期跟进事项等，后续作为相关背景参考。
  - 记忆默认开启；官方说明每晚整理当天会话，仅本人可见。
  - 用户可在设置中查看、编辑、删除或关闭记忆，也可导入其他 AI 使用习惯。
  - 官方提醒记忆可能存在概括偏差或时效性问题；依赖记忆做重要判断前应核验。
- Use for:
  - `09-model-memory/`
  - `docs/workbuddy-context-convention.md`
  - privacy and governance checklists
- Boundaries:
  - 不要把普通 Markdown 维护记录写成 WorkBuddy 官方 Memory。

### 模型配置 Model

- URL: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Model>
- Type: official
- Core facts:
  - WorkBuddy 内置主流大模型，并支持自定义模型。
  - 自定义模型可通过 UI 添加、编辑、删除；配置参数和 API Key 仅保存在本地 `workbuddy/models.json` / 兼容历史 `~/.codebuddy/models.json` 配置。
  - 使用自定义模型时，WorkBuddy 作为通信链路将输入转发给第三方模型；第三方费用、稳定性、安全性、合规性和生成结果需由用户评估。
  - 支持提供商接入、自定义 API、本地部署和自定义协议等路径。
- Use for:
  - `09-model-memory/`
  - security checklists
  - model-selection guidance
- Boundaries:
  - 模型列表和能力标记高度版本敏感；不要在正文中长期固化具体型号清单，除非同时标注检查日期。

### 数据管理

- URL: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Data>
- Type: official
- Core facts:
  - 数据管理入口位于头像 - 设置 - 数据管理。
  - 页面用于管理已分享的文件和已归档的任务。
  - 我分享的文件列表支持复制分享链接、下载文件和取消文件分享。
  - 取消分享后文件从分享列表移除，他人无法再通过原链接访问。
  - 已归档任务列表支持删除任务或取消归档。
- Use for:
  - `08-permission-security/`
  - data retention notes
  - `templates/security-checklist.md`
- Research note:
  - 2026-06-07 重新打开官方页面后确认实际 URL 为 `/Function-Description/Data`。
- Boundaries:
  - 取消分享不应扩写为删除下游副本、日志、导出文件或接收人已下载文件；不要写具体保留周期或合规承诺。

### Cloud Agent / 企业智能体

- URL: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/CloudAgent>
- Type: official
- Core facts:
  - CloudAgent 被官方描述为云端 AI Agent 运行平台，提供 Agent 生命周期管理。
  - 核心概念包括 Agent、Runtime 和 Session；Runtime 是独立云端沙箱实例，包含文件系统、终端环境、Manifest 和 Session。
  - 支持创建 Agent、配置模型/System Prompt、添加 Skill/专家/MCP、高级配置记忆与知识库、Manifest、Test Run、渠道接入、凭据管理、版本管理、Runtime/Session 管理和 Agent 评测。
  - Session 删除会永久清除对话记录和文件；评测会消耗个人积分。
- Use for:
  - `10-cloud-agent/`
  - enterprise deployment workflows
  - governance and credential-management templates
- Boundaries:
  - 不要把 Cloud Agent 写成默认人人可用；企业坐席、后台权限、渠道接入和凭据管理都应按官方说明和实际租户配置核验。

## Official Practice Case Pages

These official pages are useful for deriving case-study types, but should not be copied as our case-study prose.

Official navigation currently lists these case-study topics:

- 实践一：文件内容识别与处理
- 实践二：文档生成与编辑
- 实践三：数据分析并可视化
- 实践四：自媒体运营
- 实践五：每日自动推送资讯简报
- 实践六：远程遥控龙虾
- 实践七：零代码制作本地应用
- 实践八：自我进化 - 创建自己的 Skills
- 实践九：AI 自驱动
- 实践十：一句话，管理你的所有会议
- 实践十一：一句话，管理你的腾讯文档

Research note: exact page URLs should be opened from the official sidebar before adding links into `11-case-studies/README.md`; do not guess slugs.

## Chapter Further Reading Source Map

Use this map when adding or updating README files in each chapter.

### `00-overview/`

- Primary:
  - WorkBuddy 简介: <https://www.codebuddy.cn/docs/workbuddy/Overview>
  - 快速开始: <https://www.codebuddy.cn/docs/workbuddy/Quickstart>
- Supporting:
  - 结果查看: <https://www.codebuddy.cn/docs/workbuddy/Results>
  - Changelog: <https://www.codebuddy.cn/docs/workbuddy/Changelog>
- Notes:
  - Include a warning that this repo is unofficial and not an official docs mirror.

### `01-getting-started/`

- Primary:
  - 快速开始: <https://www.codebuddy.cn/docs/workbuddy/Quickstart>
  - 创建任务: <https://www.codebuddy.cn/docs/workbuddy/Create-Task>
  - 任务管理: <https://www.codebuddy.cn/docs/workbuddy/Task-Management>
  - 任务对话: <https://www.codebuddy.cn/docs/workbuddy/Task-Chat>
  - 结果查看: <https://www.codebuddy.cn/docs/workbuddy/Results>
- Supporting:
  - 权限模式: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes>
  - 高效使用小技巧: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Efficient-Tips>

### `02-prompt-patterns/`

- Primary:
  - 创建任务: <https://www.codebuddy.cn/docs/workbuddy/Create-Task>
  - 任务对话: <https://www.codebuddy.cn/docs/workbuddy/Task-Chat>
  - 高效使用小技巧: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Efficient-Tips>
- Supporting:
  - 专家: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Expert-Center>
  - 结果查看: <https://www.codebuddy.cn/docs/workbuddy/Results>

### `03-workflows/`

- Primary:
  - 创建任务: <https://www.codebuddy.cn/docs/workbuddy/Create-Task>
  - 任务管理: <https://www.codebuddy.cn/docs/workbuddy/Task-Management>
  - 结果查看: <https://www.codebuddy.cn/docs/workbuddy/Results>
  - 高效使用小技巧: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Efficient-Tips>
- Supporting:
  - 权限模式: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes>
  - 自动化: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide>

### `04-experts/`

- Primary:
  - 专家: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Expert-Center>
- Supporting:
  - 高效使用小技巧: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Efficient-Tips>
  - 技能: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market>
  - Cloud Agent: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/CloudAgent>

### `05-skills/`

- Primary:
  - 技能: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market>
- Supporting:
  - 权限模式: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes>
  - Changelog: <https://www.codebuddy.cn/docs/workbuddy/Changelog>
  - Cloud Agent: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/CloudAgent>

### `06-connectors/`

- Primary:
  - 连接器: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector>
- Supporting:
  - 权限模式: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes>
  - 模型配置: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Model>
  - Cloud Agent: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/CloudAgent>

### `07-automation/`

- Primary:
  - 自动化: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide>
  - Changelog: <https://www.codebuddy.cn/docs/workbuddy/Changelog>
- Supporting:
  - 权限模式: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes>
  - 高效使用小技巧: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Efficient-Tips>
  - 连接器: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector>

### `08-permission-security/`

- Primary:
  - 权限模式: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes>
  - 技能: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market>
  - 连接器: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector>
  - 自动化: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide>
  - 数据管理: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Data>
- Supporting:
  - 记忆: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Memory>
  - 模型配置: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Model>
  - Cloud Agent: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/CloudAgent>

### `09-model-memory/`

- Primary:
  - 记忆: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Memory>
  - 模型配置: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Model>
- Supporting:
  - 数据管理: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Data>
  - Changelog: <https://www.codebuddy.cn/docs/workbuddy/Changelog>

### `10-cloud-agent/`

- Primary:
  - Cloud Agent: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/CloudAgent>
- Supporting:
  - 专家: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Expert-Center>
  - 技能: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market>
  - 连接器: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector>
  - 模型配置: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Model>

### `11-case-studies/`

- Primary:
  - Official practice-case pages listed above.
  - 结果查看: <https://www.codebuddy.cn/docs/workbuddy/Results>
  - 高效使用小技巧: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Efficient-Tips>
- Supporting:
  - Capability docs relevant to each case: experts, skills, connectors, automation, permission, memory/model, Cloud Agent.
- Notes:
  - Each case study should label its workflow as practice interpretation unless the exact workflow is from official docs.

### `templates/`

- Primary:
  - 创建任务: <https://www.codebuddy.cn/docs/workbuddy/Create-Task>
  - 结果查看: <https://www.codebuddy.cn/docs/workbuddy/Results>
  - 权限模式: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes>
  - 技能: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market>
  - 连接器: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector>
  - 自动化: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide>

### `docs/` and `templates/workbuddy-context/`

- Primary:
  - 创建任务: <https://www.codebuddy.cn/docs/workbuddy/Create-Task>
  - 权限模式: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes>
  - 记忆: <https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Memory>
- Notes:
  - Must state Context Package guidance is a repository practice, not an official WorkBuddy directory standard.
  - Public reusable context belongs in `docs/` and `templates/workbuddy-context/`; local `.workbuddy/` experiments should stay ignored.
  - Must not equate Markdown maintenance notes with official Memory.

## Reference Methodology Sources

### claude-code-best-practice

- URL: <https://github.com/shanraisshan/claude-code-best-practice>
- Type: reference
- Use for:
  - Repository organization inspiration.
  - Engineering workflow framing.
  - Reusable prompt/template/checklist mindset.
- Boundaries:
  - Do not copy prose.
  - Do not present Claude Code mechanisms as WorkBuddy official capabilities.

### OpenAI Codex / AGENTS.md references

- URL: <https://platform.openai.com/docs>
- Type: reference
- Use for:
  - General agent maintenance concepts, when explicitly relevant.
- Boundaries:
  - Not a WorkBuddy source.
  - Use only for general AI engineering context and cite explicitly.

## Third-party and Community Sources

Third-party articles from TechNode, 36Kr, 少数派, V2EX, 知乎, 公众号等 may be added here when used.

- Type: third-party / community
- Use for:
  - Community observation.
  - Product perception.
  - Non-official examples.
- Boundaries:
  - Must be clearly labeled as “社区观察” or “第三方评价”。
  - Never use as official WorkBuddy fact source.
