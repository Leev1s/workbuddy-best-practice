# Assets

## What it is

本目录保存 `workbuddy-best-practice` 的仓库级多媒体内容，包括项目 Logo、README 插图、概念图和生成提示词记录。

## Current visual direction

当前主视觉已切换为参考 WorkBuddy 官方素材的猫耳 AI 办公伙伴方向：黑色面罩、青绿色眼睛、白银机器人外壳、耳机、暗色工作台、多角色 Agent 协作和办公自动化面板。它用于表达本仓库的社区实践属性，不代表 WorkBuddy 官方素材或官方背书。

## Generated assets

| Asset | File | Use |
| --- | --- | --- |
| Mascot project logo | [`images/workbuddy-practice-mascot-logo.webp`](images/workbuddy-practice-mascot-logo.webp) / [`images/workbuddy-practice-mascot-logo.png`](images/workbuddy-practice-mascot-logo.png) | 当前 README 标识、社交预览、培训封面局部元素 |
| Mascot README hero | [`images/readme-hero-mascot.webp`](images/readme-hero-mascot.webp) / [`images/readme-hero-mascot.png`](images/readme-hero-mascot.png) | 当前 README 顶部插图；猫耳多角色 Agent 办公自动化场景 |
| Mascot workflow illustration | [`images/workbuddy-practice-workflow-mascot.webp`](images/workbuddy-practice-workflow-mascot.webp) / [`images/workbuddy-practice-workflow-mascot.png`](images/workbuddy-practice-workflow-mascot.png) | 当前 README 方法论插图；解释 Task Brief、Context Package、Review、Automation 的循环 |

## Legacy generated assets

| Asset | File | Use |
| --- | --- | --- |
| Project logo v2 | [`images/workbuddy-best-practice-logo-v2.webp`](images/workbuddy-best-practice-logo-v2.webp) / [`images/workbuddy-best-practice-logo-v2.png`](images/workbuddy-best-practice-logo-v2.png) | README 标识、社交预览、培训封面局部元素；参考官方产品视觉语言的社区二创版本 |
| README hero v2 | [`images/readme-hero-v2.webp`](images/readme-hero-v2.webp) / [`images/readme-hero-v2.png`](images/readme-hero-v2.png) | README 顶部插图；参考官方文档/产品页面的白底、紫色产品图标和青绿色高光语言 |
| Project logo | [`images/workbuddy-best-practice-logo.webp`](images/workbuddy-best-practice-logo.webp) / [`images/workbuddy-best-practice-logo.png`](images/workbuddy-best-practice-logo.png) | README 标识、社交预览、培训封面局部元素 |
| README hero | [`images/readme-hero.webp`](images/readme-hero.webp) / [`images/readme-hero.png`](images/readme-hero.png) | README 顶部插图、项目介绍幻灯片 |
| Context package illustration | [`images/workbuddy-context-package.webp`](images/workbuddy-context-package.webp) / [`images/workbuddy-context-package.png`](images/workbuddy-context-package.png) | 解释 Context Package 方法论和非官方目录边界 |

## Generation notes

- 这些图片使用 GPT Image / gpt-image-2 workflow 生成，并保留提示词记录：[`prompts/gpt-image-2-assets.jsonl`](prompts/gpt-image-2-assets.jsonl)。
- mascot 系列参考了用户提供的 WorkBuddy 官网素材图：猫耳 AI 办公伙伴、多角色 Agent、黑色面罩、青绿色发光眼睛、暗色工作台和办公自动化面板；参考源仅用于社区二创设计，不作为本仓库官方素材复用。
- v2 图片参考了 WorkBuddy 官方文档页与 CodeBuddy / WorkBuddy 导航 logo 的视觉元素：紫色渐变产品图标、青绿色高光、圆角 UI 与白色抽象符号；参考源仅用于风格分析，不作为本仓库素材复用。
- 生成提示词明确要求不要复刻 WorkBuddy、腾讯、CodeBuddy、OpenAI、Claude、GitHub 等官方 Logo 或商标。
- 图片是本仓库社区视觉素材，不是 WorkBuddy 官方素材。
- README 使用 WebP 版本以减少页面体积；PNG 原图保留用于后续裁切、培训材料和再加工。

## Maintenance rules

- 新增资产时同步记录 prompt、用途、尺寸和限制。
- 不提交包含真实客户数据、内部系统界面、员工头像、未授权商标或敏感文件名的图片。
- 如果图片包含可读文字，必须人工检查文字是否正确、是否暗示官方背书、是否包含商标风险。

## Further Reading

- [README](../README.md)
- [Markdown and asset rules](../templates/workbuddy-context/markdown-asset-rules.md)
- [WorkBuddy 官方简介](https://www.codebuddy.cn/docs/workbuddy/Overview)
