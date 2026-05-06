# Documentation Template Index

Use this documentation pack as a reusable starting point for AI-assisted software projects. Replace every placeholder, example, and decision note with details from the target project before using the prompts for implementation work.

## How To Use This Template

1. Copy the `docs/` directory into a new project.
2. Replace bracketed placeholders such as `[Project Name]`, `[Primary User]`, and `[Technology Stack]`.
3. Delete sections that do not apply.
4. Add project-specific rules, constraints, and acceptance criteria.
5. Keep `00-index.md` updated when documents are added, renamed, or removed.

## Document Map

| File | Purpose |
| --- | --- |
| [01-project-overview.md](01-project-overview.md) | Project purpose, users, workflows, scope, and success criteria |
| [02-brd-business-requirements.md](02-brd-business-requirements.md) | Business goals, users, requirements, rules, and constraints |
| [03-prd-product-requirements.md](03-prd-product-requirements.md) | Product modules, feature requirements, acceptance criteria, and exclusions |
| [04-erd-database-design.md](04-erd-database-design.md) | Data entities, relationships, enums, integrity rules, and persistence notes |
| [05-api-contract.md](05-api-contract.md) | API conventions, route contracts, permissions, and error behavior |
| [06-technical-design.md](06-technical-design.md) | Architecture, module boundaries, data flow, security, and deployment design |
| [07-mvp-scope-and-backlog.md](07-mvp-scope-and-backlog.md) | MVP scope, backlog, priorities, and deferred work |
| [08-ui-ux-specification.md](08-ui-ux-specification.md) | Screen inventory, layout rules, states, responsive behavior, and interaction standards |
| [09-development-roadmap.md](09-development-roadmap.md) | Delivery sequence, dependencies, release outputs, and validation strategy |
| [10-qa-test-plan.md](10-qa-test-plan.md) | Automated and manual QA plan for release validation |
| [11-environment-setup.md](11-environment-setup.md) | Local setup, environment variables, scripts, data stores, and production commands |
| [12-configurability-analysis.md](12-configurability-analysis.md) | Settings, feature flags, module toggles, risks, and implementation phases |
| [13-test-case-matrix.md](13-test-case-matrix.md) | Function, module flow, configuration, API, and edge case test matrix |

## Template Maintenance Rules

- Keep this pack framework-neutral unless a target project has already chosen a stack.
- Prefer placeholders over invented product details.
- Mark unresolved decisions as `[Decision Needed: ...]`.
- Keep acceptance criteria measurable.
- Keep AI instructions explicit enough that another assistant can implement from the docs without guessing.
