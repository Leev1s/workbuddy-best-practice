# Changelog Watch

## Purpose

This file does **not** copy the official WorkBuddy changelog. It tracks how WorkBuddy updates may affect this repository's best practices, templates, risk checklists, and training materials.

## Official Changelog

- <https://www.codebuddy.cn/docs/workbuddy/Changelog>

## How to Use This File

- Check the official changelog before changing version-sensitive content.
- Record only updates that affect this repo's guidance, templates, safety posture, or chapter navigation.
- Do not assume a fixed behavior from old screenshots or old user experience; WorkBuddy UI and feature behavior changes frequently.
- For each item, update `sources.md` if it changes the source map.
- For risky features, keep a conservative practice even when the changelog says a bug was fixed.

## Tracking Template

Use this template when an official update changes recommended usage or risk posture.

```markdown
## Version:

- Date:
- Official summary:
- Affected areas:
  - [ ] Task creation
  - [ ] Task management / result review
  - [ ] Experts / expert teams
  - [ ] Skills
  - [ ] Connectors / MCP
  - [ ] Automation
  - [ ] Permission / sandbox
  - [ ] Memory / context
  - [ ] Model configuration
  - [ ] Cloud Agent / enterprise agent
  - [ ] Sharing / remote channels
- Best-practice impact:
- Docs to update:
- Risk notes:
```

## Current Watch Items

### 4.24.8 - 2026-06-03

- Official summary:
  - Fixes context-compression issues, historical-session loading loss, task-stop waiting state, Windows sandbox log volume, and sandbox command retry prompt behavior.
- Affected areas:
  - [x] Task management / result review
  - [x] Permission / sandbox
  - [x] Memory / context
- Best-practice impact:
  - Result-review guidance should continue to recommend checking产物、全部文件、变更和预览 after long sessions, interrupted tasks, context compression, or session reload.
  - Memory/context guidance should warn that compression and history restoration are operational features, not a substitute for explicit task briefs and final acceptance checks.
  - Permission guidance should keep recommending isolated workspaces and backups even when sandbox prompt bugs are fixed.
- Docs to update:
  - `01-getting-started/result-review.md`
  - `03-workflows/README.md`
  - `08-permission-security/permission-modes.md`
  - `09-model-memory/README.md`
- Risk notes:
  - Do not write that context compression is fully reliable.
  - Do not write that sandbox prompts always appear correctly in all environments; keep “verify before approving” language.

### 4.24.7 - 2026-06-01

- Official summary:
  - Fixes a case where some automation scheduled tasks became stuck after one run and could not trigger again.
- Affected areas:
  - [x] Automation
  - [x] Task management / result review
- Best-practice impact:
  - Automation templates should include a first-week monitoring rule: verify trigger history, output directory, and failure logs after each scheduled run.
  - Recurring automation case studies should specify a manual fallback path for missed or stuck runs.
- Docs to update:
  - `07-automation/README.md`
  - `templates/automation-template.md`
  - `11-case-studies/README.md`
- Risk notes:
  - A fixed scheduling bug does not remove the need for run history, alerting, and periodic review.

### 4.24.6 - 2026-06-01

- Official summary:
  - Updates content-filter display behavior and fixes ardot MCP injection into the wrong mode, automation skill dropdown display, and domestic integration-guide links.
- Affected areas:
  - [x] Connectors / MCP
  - [x] Automation
  - [x] Task management / result review
- Best-practice impact:
  - Connector/MCP guidance should remind users that tool availability and mode routing can change; confirm enabled tools before relying on a workflow.
  - Automation setup checklists should include “confirm selected model and skills are visible and enabled.”
- Docs to update:
  - `06-connectors/README.md`
  - `07-automation/README.md`
  - `templates/automation-template.md`
- Risk notes:
  - Do not treat MCP/tool injection as a static contract without version checks.

### 4.24.3 - 2026-05-30

- Official summary:
  - Includes fixes for skill installation, custom model request parameters, permission-mode UI/process mismatch, and several UI display problems.
- Affected areas:
  - [x] Skills
  - [x] Permission / sandbox
  - [x] Model configuration
  - [x] Task management / result review
- Best-practice impact:
  - Skill installation guides should include an installation verification step.
  - Permission-mode guidance should say users need to check the visible mode and the actual confirmation prompts before risky actions.
  - Model guidance should avoid hard-coding assumptions about custom model behavior; instruct users to run a small test task after configuration.
- Docs to update:
  - `05-skills/README.md`
  - `08-permission-security/permission-modes.md`
  - `09-model-memory/README.md`
- Risk notes:
  - Prior bugs around permission-mode sync justify keeping conservative defaults even after a fix.

### 4.24.2 - 2026-05-29

- Official summary:
  - Adds sharing/project invitation/OAuth management, sidebar fold and task pin/archive/filter interactions, MITM CA trust handling, tool-call loop detection, skill-description priority, artifact sharing changes, automation peak scheduling optimization, and many fixes across automation, connectors, history, sandbox, expert teams, and sharing.
- Affected areas:
  - [x] Task management / result review
  - [x] Experts / expert teams
  - [x] Skills
  - [x] Connectors / MCP
  - [x] Automation
  - [x] Permission / sandbox
  - [x] Sharing / remote channels
- Best-practice impact:
  - Result-review guidance should include sharing review: confirm filename/title/content before sharing externally.
  - Expert-team guidance should include cost and coordination checks for multi-expert tasks.
  - Automation guidance should mention peak-time scheduling and unnecessary model calls as operational concerns.
  - Connector guidance should cover OAuth app management and authorization review.
- Docs to update:
  - `03-workflows/README.md`
  - `04-experts/README.md`
  - `06-connectors/README.md`
  - `07-automation/README.md`
  - `08-permission-security/README.md`
- Risk notes:
  - Sharing and OAuth expand the blast radius of a task; include explicit review before external distribution.

### 4.24.0 - Recent baseline for v0.1

- Official summary:
  - Adds or improves custom expert management, MCP tool-call progress/resource support, connector “go try” entry, input-box permission-mode entry and Full Access confirmation, workspace folding, artifact sharing, file preview auto-refresh, Skill/Marketplace installation updates, automation improvements, sandbox security strategy, expert-team stability, and many state/history/model fixes.
- Affected areas:
  - [x] Task creation
  - [x] Task management / result review
  - [x] Experts / expert teams
  - [x] Skills
  - [x] Connectors / MCP
  - [x] Automation
  - [x] Permission / sandbox
  - [x] Model configuration
  - [x] Sharing / remote channels
- Best-practice impact:
  - Treat 4.24.x as the v0.1 baseline for current UI/functionality claims.
  - Any article about Full Access, connector testing, Skill installation, artifact sharing, preview, expert teams, or automation should cite official docs and check Changelog.
  - Add acceptance criteria around file preview refresh and artifact sharing, but do not assume these features are always available across old clients.
- Docs to update:
  - `sources.md`
  - all capability chapter README files
  - `templates/review-checklist.md`
  - `templates/security-checklist.md`
- Risk notes:
  - Use “as of official Changelog checked on 2026-06-06” when writing version-sensitive summaries.

## Watch Categories for Future Updates

### Permission / Sandbox

- Watch for changes to default permission, Full Access, workspace boundary, command execution, script prompts, sandbox bypass, or OS-specific sandbox behavior.
- Update:
  - `08-permission-security/`
  - `templates/security-checklist.md`
  - `templates/workbuddy-context/repository-review-checklist.md`

### Skills / Connectors / MCP

- Watch for new install paths, trust prompts, official recommended Skill status, connector authorization scopes, OAuth management, MCP config behavior, and third-party data-sharing changes.
- Update:
  - `05-skills/`
  - `06-connectors/`
  - `templates/skill-evaluation-template.md`
  - `templates/connector-evaluation-template.md`

### Automation

- Watch for scheduling behavior, retry behavior, max runtime, failure details, result delivery, push-to-mini-program, skill/model selection, and unattended-execution changes.
- Update:
  - `07-automation/`
  - `templates/automation-template.md`
  - automation case studies

### Memory / Context

- Watch for memory extraction frequency, visibility, edit/delete controls, import behavior, context compression, history replay, and long-session recovery.
- Update:
  - `09-model-memory/`
  - `docs/workbuddy-context-convention.md`
  - prompt and review templates

### Model Configuration

- Watch for built-in model list, Auto routing, custom model UI, local config paths, API Key storage, local model support, cost notes, and content-filter behavior.
- Update:
  - `09-model-memory/`
  - source map entries
  - security checklist

### Cloud Agent

- Watch for enterprise seat requirements, Runtime/Session lifecycle, Manifest schema, credentials, channel integrations, API access, evaluation, version/snapshot behavior, and deletion semantics.
- Update:
  - `10-cloud-agent/`
  - enterprise governance guidance
  - credential and channel review templates

## Further Reading

- [sources.md](sources.md)
- [WorkBuddy 官方更新日志](https://www.codebuddy.cn/docs/workbuddy/Changelog)
