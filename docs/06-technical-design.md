# 06 - Technical Design

## Architecture

[Describe the chosen architecture and why it fits the project.]

```text
[Client/UI]
  -> [Application/API Layer]
  -> [Domain/Service Layer]
  -> [Data Access / Integration Layer]
  -> [Data Store / External Services]
```

## Technology Stack

| Layer | Technology | Notes |
| --- | --- | --- |
| Frontend | [Technology] | [Notes] |
| Backend | [Technology] | [Notes] |
| Data | [Technology] | [Notes] |
| Styling | [Technology] | [Notes] |
| Testing | [Technology] | [Notes] |
| Deployment | [Technology] | [Notes] |

## Module Boundaries

| Module | Responsibility | Owns |
| --- | --- | --- |
| `[module]` | [Responsibility] | [Routes, services, data, UI, jobs] |
| `[module]` | [Responsibility] | [Routes, services, data, UI, jobs] |
| `[shared]` | [Shared responsibility] | [Utilities, types, clients] |

## Application Routes / Entry Points

| Route / Entry Point | Purpose | Access |
| --- | --- | --- |
| `[route]` | [Purpose] | [Public/protected/role] |
| `[route]` | [Purpose] | [Public/protected/role] |

## Key Data Flows

### [Workflow Name]

1. [Actor starts workflow.]
2. [System loads or validates data.]
3. [Domain service applies business rules.]
4. [Persistence or external integration occurs.]
5. [System returns result and updates UI/state.]

### [Workflow Name]

1. [Actor starts workflow.]
2. [System loads or validates data.]
3. [Domain service applies business rules.]
4. [Persistence or external integration occurs.]
5. [System returns result and updates UI/state.]

## Security Design

- [Authentication rule]
- [Authorization rule]
- [Secret handling rule]
- [Input validation rule]
- [Audit/logging rule]
- [Privacy or data retention rule]

## State And Calculation Design

- [Source of truth rule]
- [Client state rule]
- [Server state or cache rule]
- [Calculation or business rule ownership]
- [Concurrency or idempotency rule]

## Integration Design

| Integration | Direction | Purpose | Failure Behavior |
| --- | --- | --- | --- |
| [Service] | [Inbound/outbound] | [Purpose] | [Fallback or error behavior] |

## Deployment Design

Production-like deployments require:

- [Runtime]
- [Data store]
- [Required environment variables]
- [Build command]
- [Migration or setup command]
- [Start command]

Standard flow:

```bash
[install command]
[generate/build preparation command]
[migration command]
[build command]
[start command]
```

## Operational Constraints

- [Constraint]
- [Constraint]
- [Constraint]

## Extension Points

- [Likely future module or integration]
- [Scaling or performance extension]
- [Configuration or customization extension]
