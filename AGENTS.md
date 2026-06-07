# AGENTS.md

## Project Overview

This repository is an unofficial Chinese-first best-practice knowledge base for WorkBuddy-style workplace agents and enterprise office automation. Maintain it as a structured, reusable methodology library, not as an official docs mirror.

## Language Rules

- Main language: 简体中文。
- Keep key technical terms in English when useful: Agent, Skill, Connector, MCP, Automation, Memory, Cloud Agent, Permission Mode, Full Access。
- Use clear, practical language for enterprise users and AI Agent practitioners.

## Source Policy

- Official facts must primarily come from WorkBuddy official docs: <https://www.codebuddy.cn/docs/workbuddy/Overview>.
- For version-sensitive content, check the official Changelog first.
- Third-party articles are only community observations or examples, never official facts.
- Do not fabricate official capabilities, limitations, roadmaps, pricing, or security guarantees.

## Writing Style

Each article should, where applicable, include:

1. What it is
2. When to use it
3. How to use it
4. Best practices
5. Common mistakes
6. Security / permission notes
7. Further Reading

Separate official facts, practical interpretation, and risk reminders when possible. Avoid marketing tone and large copied passages.

## File Structure Policy

- Do not create `.workbuddy/` in the public repo by default. If a team uses `.workbuddy/` locally, label it experimental / repository convention, not a WorkBuddy official standard.
- Use `docs/workbuddy-context-convention.md` and `templates/workbuddy-context/` for public context-package guidance and reusable templates.
- Do not claim WorkBuddy automatically reads `.workbuddy/AI_AGENT_INSTRUCTIONS.md` or any other local Markdown file unless official docs explicitly say so.
- Do not equate repository Markdown memory files with WorkBuddy official Memory.
- Prefer small, focused Markdown files under thematic directories.
- Do not create many empty placeholder files.
- Add navigation links when adding new articles.
- Templates must be directly copyable.

## Citation / Reference Policy

- Link official docs in `Further Reading` and `sources.md`.
- Attribute third-party viewpoints as “社区观察” or “第三方评价”。
- GitHub personal repos can be inspiration, not WorkBuddy official fact sources.

## Quality Checklist

Before finishing a change:

- Markdown title hierarchy is valid.
- Internal links use relative paths and resolve.
- Terms are consistent.
- Every article has `Further Reading`.
- Security / permission notes exist for risky capabilities.
- No large-scale official docs mirroring.

## Anti-Hallucination Rules

- If official docs do not state a capability, write it as practice advice, hypothesis, or leave it out.
- Do not map Claude Code mechanisms to WorkBuddy as official equivalents.
- Do not assume third-party Skills, MCP servers, Connectors, APIs, or scripts are safe.
- Do not store temporary memories, run logs, caches, task artifacts, private context, or sensitive data in committed paths.

## Maintenance Workflow

1. Read this file first.
2. Read `README.md` and relevant section README files.
3. Check official docs and Changelog for new or version-sensitive WorkBuddy facts.
4. Make small, reviewable changes.
5. Run basic Markdown and link checks where possible.
6. Commit with a clear message.
