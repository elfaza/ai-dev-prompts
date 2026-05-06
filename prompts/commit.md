---
description: Format and prepare a Conventional Commit for the current changes
argument-hint: [optional commit intent or scope]
allowed-tools: [Read, Glob, Grep, Bash]
---

# Commit Formatter

Use this command to inspect the current git changes and produce a clean Conventional Commit message.

## Arguments

The user invoked this command with:

```text
$ARGUMENTS
```

Treat the arguments as optional context for the intended commit type, scope, or summary. Do not invent behavior that is not supported by the diff.

## Workflow

1. Run `git status --short` to identify changed files.
2. Prefer the staged diff with `git diff --cached --stat` and `git diff --cached`.
3. If nothing is staged, inspect unstaged changes with `git diff --stat` and `git diff`, then explain that the message is based on unstaged changes.
4. Separate unrelated changes. If the diff contains multiple logical changes, recommend separate commits and provide one message per logical group.
5. Produce a Conventional Commit message using this format:

```text
type(scope): summary

body
```

Use the body only when it adds useful context. Keep the summary imperative, lowercase, and under 72 characters.

## Commit Types

Prefer these types:

- `feat`: user-facing or domain behavior added
- `fix`: bug fix or corrected behavior
- `test`: tests added or changed
- `docs`: documentation-only changes
- `refactor`: internal code change with no behavior change
- `style`: formatting or presentation-only code changes
- `chore`: tooling, configuration, dependency, or maintenance changes

Use a scope when it makes the message clearer, such as `checkout`, `auth`, `catalog`, `orders`, `docs`, `tests`, `config`, or `deps`.

## Output

Return:

- The recommended commit message in a code block.
- A brief rationale tied to the changed files.
- Any split-commit recommendation if the current diff mixes unrelated work.

Do not create the commit unless the user explicitly asks you to commit.
