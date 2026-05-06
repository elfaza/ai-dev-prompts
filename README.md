# AI Dev Prompts

Reusable custom AI commands and documentation templates for software development projects.

This repository is a starter kit for creating AI-assisted project workflows. It includes portable command prompts in `prompts/` and a project documentation template in `docs/` that other AI projects can copy, fill in, and use as implementation context.

## Repository Structure

```text
.
├── docs/
│   ├── 00-index.md
│   ├── 01-project-overview.md
│   ├── ...
│   └── 13-test-case-matrix.md
└── prompts/
    ├── commit.md
    └── develop.md
```

## What This Template Provides

- reusable AI command prompts
- a standard documentation pack for new projects
- placeholders for product, business, architecture, API, data, UX, QA, setup, and deployment decisions
- a consistent structure that AI coding agents can read before implementation

## Available Prompts

### `prompts/commit.md`

Formats a Conventional Commit message from the current git changes.

Use it when you want an AI assistant to inspect changes, detect split-commit opportunities, and produce a clean commit message.

### `prompts/develop.md`

Guides an AI assistant through implementing a development task using the target project's local documentation and code patterns.

Use it after the target project has filled in the `docs/` template or has equivalent project documentation.

## Documentation Template

The `docs/` directory is intentionally project-agnostic. Copy it into another project, then replace placeholders like `[Project Name]`, `[Module Name]`, `[Technology]`, and `[Decision Needed: ...]` with real project details.

Recommended setup flow:

1. Fill in `docs/01-project-overview.md`.
2. Define business and product requirements in `docs/02-brd-business-requirements.md` and `docs/03-prd-product-requirements.md`.
3. Document data, API, architecture, and UX decisions in `docs/04-*` through `docs/08-*`.
4. Define roadmap, QA, setup, deployment, and test cases in `docs/09-*` through `docs/13-*`.
5. Keep `docs/00-index.md` updated as the project evolves.

## Prompt Format

Each prompt is a Markdown file with optional command metadata at the top:

```yaml
---
description: Short command description
argument-hint: [expected arguments]
allowed-tools: [Read, Glob, Grep, Bash]
---
```

The body should define:

- command purpose
- argument handling
- workflow steps
- output requirements
- safety rules

## Adding a New Prompt

1. Create a new Markdown file in `prompts/`.
2. Use a short, action-oriented filename, such as `review.md` or `debug-ci.md`.
3. Add metadata when supported by the target AI tool.
4. Keep the workflow specific enough to be repeatable.
5. Document expected output so command results stay consistent.

## Template Principles

- Prefer placeholders over invented project details.
- Keep commands reusable across frameworks and domains.
- Make project-specific decisions explicit in docs before implementation.
- Use measurable acceptance criteria and concrete validation commands.
- Include safety rules for commits, destructive commands, credentials, permissions, and production data.

## Usage

Copy `prompts/` and `docs/` into a project that needs reusable AI development workflows. Fill in the docs first, then run the prompts from the target AI coding tool.
