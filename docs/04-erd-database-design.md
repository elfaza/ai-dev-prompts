# 04 - ERD: Database Design

## Overview

[Describe the persistence model, primary data ownership boundaries, and data stores used by the project.]

If the project does not use a database, replace this document with the relevant state, file, cache, or external data model.

## Entity Relationship Summary

```text
[Entity A] 1--many [Entity B]
[Entity B] many--1 [Entity C]
[Entity C] 1--many [Entity D]
```

## Enums

| Enum | Values | Purpose |
| --- | --- | --- |
| `[EnumName]` | `[value_one]`, `[value_two]` | [Purpose] |
| `[EnumName]` | `[value_one]`, `[value_two]` | [Purpose] |

## Core Tables / Collections

### `[entity_name]`

Purpose: [What this entity represents.]

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| `id` | [Type] | Yes | [Identifier strategy] |
| `[field]` | [Type] | [Yes/No] | [Constraints or meaning] |
| `created_at` | [Type] | Yes | [Timestamp behavior] |
| `updated_at` | [Type] | Yes | [Timestamp behavior] |

Relationships:

- [Relationship to another entity]
- [Relationship to another entity]

Integrity rules:

- [Unique constraint, foreign key, validation, or cascade rule]
- [Data retention or deletion rule]

### `[entity_name]`

Purpose: [What this entity represents.]

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| `id` | [Type] | Yes | [Identifier strategy] |
| `[field]` | [Type] | [Yes/No] | [Constraints or meaning] |
| `created_at` | [Type] | Yes | [Timestamp behavior] |
| `updated_at` | [Type] | Yes | [Timestamp behavior] |

Relationships:

- [Relationship to another entity]

Integrity rules:

- [Unique constraint, foreign key, validation, or cascade rule]

## Reporting Data Sources

| Report / View | Source Entities | Notes |
| --- | --- | --- |
| [Report name] | [Entities] | [Aggregation or filtering rules] |

## Migration Notes

- [Migration rule or compatibility requirement]
- [Seed data requirement]
- [Backfill or data cleanup note]
