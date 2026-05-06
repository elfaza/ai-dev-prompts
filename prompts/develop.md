---
description: Develop a task against the current project's docs and codebase patterns
argument-hint: [task to implement] [optional: --single-agent]
allowed-tools: [Read, Glob, Grep, Bash, Edit, Write]
---

# Project Development

Use this command to implement a development task in the current project while following that project's local documentation, architecture, and testing standards.

## Arguments

The user invoked this command with:

```text
$ARGUMENTS
```

Treat all arguments as the development task. Use parallel sub-agents by default when the active runtime supports them and the work has separable concerns. If the arguments include `--single-agent`, do the work with one agent only.

## Standard Project Documents

This command expects each project to keep a standardized documentation package. Before planning or editing, read:

1. Project instructions when present: `AGENTS.md`, `CLAUDE.md`, `.cursorrules`, `.github/copilot-instructions.md`.
2. The documentation index: `docs/00-index.md`.

Then read only the standard docs that directly affect the task:

- Project purpose and scope: `docs/01-project-overview.md`
- Business rules and operational requirements: `docs/02-brd-business-requirements.md`
- Product modules, feature requirements, and acceptance criteria: `docs/03-prd-product-requirements.md`
- Data model, persistence, or migration work: `docs/04-erd-database-design.md`
- API, integration, route, or contract work: `docs/05-api-contract.md`
- Architecture, module boundaries, data flow, security, and deployment design: `docs/06-technical-design.md`
- MVP scope, backlog, priority, or sequencing work: `docs/07-mvp-scope-and-backlog.md`
- UI, UX, styling, accessibility, or user workflow work: `docs/08-ui-ux-specification.md`
- Roadmap, release sequencing, or delivery planning: `docs/09-development-roadmap.md`
- Test planning and acceptance coverage: `docs/10-qa-test-plan.md`, `docs/13-test-case-matrix.md`
- Environment, setup, scripts, data stores, or local services: `docs/11-environment-setup.md`
- Settings, feature flags, module toggles, or project configurability: `docs/12-configurability-analysis.md`

Always read `docs/10-qa-test-plan.md` before implementation when code behavior changes, tests change, public interfaces change, or the task has acceptance criteria. Also read `docs/13-test-case-matrix.md` when the task touches a workflow, API, permission, edge case, or release-blocking behavior. For docs-only edits that cannot affect behavior, state why the test plan is not applicable.

Before changing framework conventions, routing, caching, rendering behavior, migrations, generated clients, build configuration, or deployment behavior, also read the relevant local framework or tool docs when they are available in the repository.

If `docs/00-index.md` is missing, fall back to project context discovery:

1. Read available project guidance files such as `AGENTS.md`, `CLAUDE.md`, `README.md`, and `CONTRIBUTING.md`.
2. Search `docs/` for files whose names match the task area, such as `overview`, `brd`, `prd`, `requirements`, `architecture`, `technical`, `api`, `database`, `schema`, `erd`, `ui`, `ux`, `test`, `qa`, `release`, `deployment`, `setup`, `configuration`, or `roadmap`.
3. State that the standardized docs package is missing and list the fallback docs used.

Do not begin implementation until the relevant docs have been read and their constraints are reflected in the plan.

Do not paste large document sections into the plan. Cite the relevant files and summarize only constraints that affect the implementation.

## Operating Rules

1. Work only on the requested task unless another change is required to make it correct.
2. Preserve documented product rules, architecture boundaries, security constraints, and out-of-scope decisions.
3. If project docs conflict with code or with each other, stop and identify the conflict before implementation unless there is an obvious conservative interpretation.
4. Follow existing project patterns for file layout, naming, state management, API boundaries, validation, error handling, and tests.
5. Treat persisted data and backend services as the source of truth unless the project architecture says otherwise.
6. When schema, migrations, generated clients, seed data, or persisted workflows change, update all affected layers together and verify the real local development data path when practical.
7. When protected workflows change, verify authentication, authorization, server-side enforcement, and UI access controls together.
8. For money, quantities, dates, permissions, and other high-risk business rules, use existing project helpers and documented conventions. Do not introduce ad hoc calculations or parsing when the project has a standard path.
9. Backend validation errors must map to clear caller or UI error states without exposing sensitive internals.
10. Keep commits grouped by logical purpose. Use Conventional Commit messages in the form `type(scope): summary` when a scope is useful, or `type: summary` when it is not.
11. When changing shared utilities, services, stores, schemas, or types, check call sites and update affected tests.
12. A task is complete only when implementation, relevant tests, validation, documentation compliance, and final worktree review are complete.
13. Do not refactor unrelated code unless the user explicitly asks or the refactor is necessary to complete the requested behavior safely.

## Development Workflow

Follow this workflow:

1. Restate the task in one concise sentence.
2. Read the standard project docs or fallback docs that apply to the task.
3. Produce a concise document analysis before implementation.
4. Inspect existing files and identify the smallest coherent implementation path.
5. Create task-specific test specs from `docs/10-qa-test-plan.md`, `docs/13-test-case-matrix.md`, and adjacent test patterns.
6. Create a short implementation checklist mapped to the relevant standard docs, code areas, and validation.
7. Before editing, state which files or areas will change and why.
8. Implement the change using existing project patterns.
9. Add or update focused tests when the project has an adjacent test pattern or the risk justifies coverage.
10. Run the most specific useful validation available, such as targeted tests, full tests, lint, typecheck, build, or live workflow checks.
11. If validation fails, fix the cause and rerun the relevant checks.
12. Review the final diff for accidental scope creep, missed docs, missing tests, and unrelated changes.
13. Finish with a concise summary of changed files, validation results, and any remaining blockers.

## Parallel Agent Workflow

Use parallel sub-agents by default when the active runtime allows it and the task has separable workstreams.

Use fewer or no sub-agents when:

- The runtime blocks sub-agent usage.
- The task is docs-only, single-file, or too small to benefit from delegation.
- The next critical-path action depends on context that must be gathered locally first.
- The user asks for single-agent work or passes `--single-agent`.

When using sub-agents:

1. Define ownership before work starts, such as backend, frontend, data, docs, or QA.
2. Keep write scopes distinct to avoid conflicts.
3. Publish a shared kickoff note with selected docs, expected behavior, test specs, acceptance checklist, and interface contracts.
4. Require each implementation agent to report files changed, behavior implemented, validation run, contract changes, risks, and blockers.
5. Perform final integrated QA from the merged result, not from isolated agent claims.
6. Route QA findings back to the owning agent only when that materially speeds up the fix.

## Document Analysis

Before implementation, produce a concise task-specific analysis with these sections:

- `Docs Used`: list only the project docs read for this task.
- `Product/Business Rules`: summarize domain rules and workflow requirements that apply.
- `Scope Boundary`: summarize in-scope, out-of-scope, dependency, and acceptance requirements.
- `Architecture Rules`: summarize relevant module boundaries, data ownership, framework conventions, and integration contracts.
- `UI/UX Rules`: include only when the task changes user experience.
- `Security/Permissions Rules`: include when auth, authorization, secrets, privacy, or protected workflows are involved.
- `Task-Specific Test Specs`: list relevant existing test cases or proposed specs grouped by unit, integration, API, UI, flow, and edge cases.
- `Agent Coordination`: state whether sub-agents are needed and why.
- `Implementation Implications`: translate the findings into concrete files, modules, risks, and validation needs.
- `Acceptance Checklist`: list the checks that must pass before the task is considered complete.

Keep the analysis tied to the selected task. Do not summarize unrelated documentation.

## Documentation Compliance Loop

After implementation, compare the result against:

1. The project instructions and docs used for the task.
2. Architecture and API contracts affected by the change.
3. UI/UX docs when the task changes user-facing workflows.
4. Security and permissions expectations when protected behavior changes.
5. Test specs and adjacent testing patterns.
6. Runtime or database readiness when schema, persisted data, routes, services, or external integrations changed.
7. Accidental out-of-scope work.

Fix any mismatch or clearly report a real blocker.

## Final Response

Finish with:

- What changed, with file paths.
- Which validation commands ran and their results.
- Whether tests were added, updated, or intentionally not changed.
- A brief documentation compliance result.
- A worktree check that separates task changes from pre-existing unrelated changes.
- Any remaining blocker or follow-up, only if one exists.
