# Project Agent Starter

A reusable, framework-agnostic starter template for AI coding agents.

A lightweight set of persistent agent instructions and reusable workflows designed to help AI coding agents work autonomously, clarify requirements when necessary, preserve code quality, and perform safe, evidence-based codebase cleanup.

English | [繁體中文](i18n/zh-TW/README.md)

## Features

- **Autonomous Development** — Work independently on low-risk, reversible tasks.
- **Conditional Requirements Clarification** — Ask questions only when unresolved decisions materially affect outcomes.
- **Efficient Verification** — Run relevant checks without repetitive or unnecessary testing.
- **Safe Code Cleanup** — Require evidence before removing legacy code or tests.
- **Agent Instruction Maintenance** — Keep persistent project rules concise and up to date.
- **Deep Codebase Audit** — Use an optional six-phase workflow for major cleanup tasks.

## Quick Start

1. Click **Use this template** on GitHub.
2. Create a new repository from the template.
3. Review [AGENTS.md](AGENTS.md) and adapt it to your project.
4. Add project-specific requirements when necessary.
5. Start working with your AI coding agent.

For major cleanup tasks, ask your agent to read `prompts/SAFE_CODEBASE_AUDIT_EN.md` and produce a read-only audit report before making any changes.

This repository contains Markdown templates; no installation or build is required. In an existing project, merge the rules into your current instructions instead of overwriting them. Add real build/test commands, compatibility commitments, and project boundaries as they become known. If your agent does not automatically read `AGENTS.md`, explicitly ask it to read the file or reference it from that tool's instruction entry point.

## Repository Layout

```text
project-agent-starter/
├── AGENTS.md
├── REQUIREMENTS.md
├── AGENTS-MAINTENANCE.md
├── README.md
├── LICENSE
├── prompts/
│   └── SAFE_CODEBASE_AUDIT_EN.md
└── i18n/zh-TW/
    ├── AGENTS.md
    ├── REQUIREMENTS.md
    ├── AGENTS-MAINTENANCE.md
    ├── README.md
    └── prompts/
        └── SAFE_CODEBASE_AUDIT_ZH_TW.md
```

| File | Purpose | When to use |
| --- | --- | --- |
| [AGENTS.md](AGENTS.md) | Persistent working rules and Safe Code Cleanup Policy | Everyday development |
| [REQUIREMENTS.md](REQUIREMENTS.md) | Requirements clarification procedure | Material unresolved decisions |
| [AGENTS-MAINTENANCE.md](AGENTS-MAINTENANCE.md) | Rules for maintaining agent instructions | Durable project conventions change |
| [Audit prompt](prompts/SAFE_CODEBASE_AUDIT_EN.md) | Evidence-based six-phase audit and cleanup | Explicit major cleanup tasks |

`REQUIREMENTS.md` currently provides a clarification guide, not a completed product specification. Keep confirmed product requirements and acceptance criteria in your project's own specifications and link them from your instructions.

## Run a Safe Audit

Copy this request into your agent conversation:

```text
Read prompts/SAFE_CODEBASE_AUDIT_EN.md and follow its six-phase workflow to audit this project. For this run, complete only read-only analysis and a cleanup plan. Do not modify or delete any files. Wait for my review and explicit approval before executing changes.
```

The workflow covers project understanding, deep auditing, evidence and risk assessment, an approval gate, targeted validation, and a final report. Audit-only runs stop at the plan and report; implementation and post-change validation follow only after approval. Approve specific batches with their scope, verification, and rollback plan. Uncertain candidates stay in place, and genuine bugs are fixed rather than hidden by weakened tests.

## Language Versions

English files at the repository root and in `prompts/` are the canonical versions. Traditional Chinese translations live in [i18n/zh-TW/](i18n/zh-TW/README.md).

For a Chinese-first project, copy the three Chinese rule files into your project root and the Chinese audit prompt into your project's `prompts/` directory. Review existing files before replacing them. Keeping a translation under `i18n/` alone does not select it as the project's root instruction file.

To use the Chinese audit prompt without moving files, ask the agent to read `i18n/zh-TW/prompts/SAFE_CODEBASE_AUDIT_ZH_TW.md`; the audit still applies to the current project root.

## Contributing and Translation Maintenance

Issues and pull requests are welcome. Keep changes focused and framework-agnostic. Update the English source and corresponding Traditional Chinese translation together, preserving the same safety boundaries and approval conditions. If translation work remains, identify the affected sections in the pull request.

Before submitting, check relative links, example paths, language parity, and all six audit phases. Keep one-off workflows in `prompts/` rather than expanding the always-loaded instructions. This documentation-only template has no application test suite; projects using it should run their own relevant checks.

## License

[MIT License](LICENSE). You may use, modify, and redistribute the template, including commercially, subject to the license terms. Preserve its copyright and permission notice when redistributing it.
