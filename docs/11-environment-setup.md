# 11 - Environment Setup

## Requirements

- Runtime: [Node.js, Python, Go, Java, etc.]
- Package manager: [npm, pnpm, yarn, pip, uv, cargo, etc.]
- Database or data store: [Database, none, local file, external service]
- Local services: [Docker, emulator, mock server, queue, cache]
- Required accounts or API keys: [Services]

## Install Dependencies

```bash
[install command]
```

## Local Services

```bash
[command to start database or services]
```

## Environment Variables

Create `[environment file name]`:

```bash
[VARIABLE_NAME]=[value]
[VARIABLE_NAME]=[value]
[SECRET_NAME]=[local development secret]
```

Do not commit real secrets.

## Data Setup

```bash
[migration command]
[seed command]
```

## Start Development Server

```bash
[dev command]
```

Local URL: `[http://localhost:port]`

## Scripts

| Script | Purpose |
| --- | --- |
| `[script]` | [Purpose] |
| `[script]` | [Purpose] |
| `[script]` | [Purpose] |

## Production-Like Deployment Flow

```bash
[install command]
[generate or prepare command]
[migration command]
[build command]
[start command]
```

## Database Notes

- [Migration policy]
- [Seed data policy]
- [Backup or restore note]
- [Local reset note]

## Release Validation

```bash
[lint command]
[test command]
[typecheck command]
[build command]
```

## Known Local Limits

- [Limit]
- [Limit]
- [Limit]
