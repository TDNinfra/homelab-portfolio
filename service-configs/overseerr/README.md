# Overseerr

## What it is
Overseerr is a media request and approval system for Plex libraries.

## Why I use it
To allow household users to request content that flows through Radarr/Sonarr.

## How it integrates in my stack
- Talks to Plex, Radarr, Sonarr APIs.
- Reads library structure via `/data/media`.

## Key features / config choices
- Minimal privileges, capped logs.
- `.env` for any secrets if needed.

## Security & backup
- Do not expose Overseerr publicly without auth/Zero Trust.
- Back up `/config`.

## Ports
- 5055/tcp → Web UI

## Quick start
1. Copy `.env.example` → `.env` and fill values (IDs, paths, tokens).
2. Adjust `DOCKERCONFDIR` and `DOCKERSTORAGEDIR` to your host.
3. Launch:
```bash
docker compose up -d
```
