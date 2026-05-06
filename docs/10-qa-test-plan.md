# 10 - QA Test Plan

## QA Objective

[Describe what quality means for this project and what must be verified before release.]

## Test Types

| Type | Purpose | Tool / Method |
| --- | --- | --- |
| Unit | Verify isolated business logic and utilities | [Tool] |
| Integration | Verify module boundaries, persistence, and external services | [Tool] |
| API / Contract | Verify request, response, auth, and error behavior | [Tool] |
| UI / Component | Verify user-facing states and interactions | [Tool] |
| End-to-End | Verify critical user workflows | [Tool] |
| Manual QA | Verify exploratory, visual, and operational readiness | [Checklist] |

## Automated Test Areas

### [Module Name]

- [Happy path]
- [Validation or error case]
- [Permission or state transition case]
- [Edge case]

### [Module Name]

- [Happy path]
- [Validation or error case]
- [Permission or state transition case]
- [Edge case]

### Shared Behavior

- [Utility or helper behavior]
- [Configuration behavior]
- [Security or permission behavior]

## Manual QA Checklist

- [Critical workflow works from start to finish.]
- [Invalid input shows clear errors.]
- [Protected actions require correct access.]
- [Empty, loading, and error states are usable.]
- [Data persists correctly after refresh or restart.]
- [Logs and monitoring capture important failures.]

## Responsive QA

- [Small mobile viewport]
- [Large mobile viewport]
- [Tablet viewport]
- [Desktop viewport]
- [Wide desktop viewport]

## Release Validation Commands

```bash
[install command]
[lint command]
[test command]
[typecheck command]
[build command]
```

## Defect Severity

| Severity | Definition |
| --- | --- |
| Critical | Blocks release, corrupts data, breaks security, or prevents core workflow |
| High | Breaks important workflow with no acceptable workaround |
| Medium | Degrades workflow but has a workaround |
| Low | Cosmetic, copy, or minor polish issue |

## Exit Criteria

- [All P0 tests pass.]
- [Known critical and high defects are resolved.]
- [Release validation commands pass.]
- [Manual QA checklist is complete.]
- [Documentation reflects implemented behavior.]
