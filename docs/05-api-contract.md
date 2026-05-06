# 05 - API Contract

## Overview

[Describe the API style, transport protocol, versioning strategy, and client/server ownership.]

Examples: REST, GraphQL, RPC, server actions, SDK-only integration, event-driven messages.

## Authentication Model

- Authentication mechanism: [session, token, OAuth, API key, none]
- Authorization model: [roles, permissions, ownership, tenant rules]
- Public endpoints: [List public endpoints]
- Protected endpoints: [List protected endpoint groups]

## Response Conventions

Success response:

```json
{
  "data": {}
}
```

Error response:

```json
{
  "error": {
    "code": "ERROR_CODE",
    "message": "Human-readable message"
  }
}
```

Update these examples to match the target project's actual response shape.

## Common Status Codes

| Status | Meaning |
| --- | --- |
| `200` | Successful read or mutation |
| `201` | Resource created |
| `400` | Invalid request |
| `401` | Unauthenticated |
| `403` | Unauthorized |
| `404` | Resource not found |
| `409` | Conflict or invalid state transition |
| `422` | Validation failed |
| `500` | Unexpected server error |

## Route Summary

### `[Resource or Feature]`

| Method | Path | Permission | Purpose |
| --- | --- | --- | --- |
| `GET` | `/api/[resource]` | [Permission] | [Purpose] |
| `POST` | `/api/[resource]` | [Permission] | [Purpose] |
| `PATCH` | `/api/[resource]/:id` | [Permission] | [Purpose] |
| `DELETE` | `/api/[resource]/:id` | [Permission] | [Purpose] |

Request notes:

- [Validation rule]
- [Required fields]
- [Idempotency or concurrency rule]

Response notes:

- [Response fields]
- [Side effects]

### `[Resource or Feature]`

| Method | Path | Permission | Purpose |
| --- | --- | --- | --- |
| `GET` | `/api/[resource]` | [Permission] | [Purpose] |
| `POST` | `/api/[resource]` | [Permission] | [Purpose] |

## Error Behavior

- Validation errors must identify the invalid field when practical.
- Authorization errors must not expose sensitive resource existence.
- Server errors must be logged with context but return safe public messages.
- External service failures must map to actionable client states.

## Connectivity Rules

- [Online/offline behavior]
- [Retry and timeout policy]
- [Caching or stale data behavior]
- [Rate limit or quota behavior]
