# Prowlarr

## What it is
Prowlarr is an indexer manager/proxy that centralizes indexer configuration for Radarr/Sonarr/etc.

## Why I use it
To keep a single source of truth for indexers and API keys while feeding multiple apps.

## How it integrates in my stack
- Feeds indexers to Radarr/Sonarr/Readarr via the Prowlarr API.
- Shares `/config` for backups.

## Key features / config choices
- Runs with `PUID/PGID` to match NAS permissions.
- Logging capped via json-file options.
- All secrets live in `.env`.

## Security & backup
- Keep API keys in the app UI; configs are backed up via NAS/B2.
- Do not publish indexer URLs or keys.

## Ports
- 9696/tcp → Web UI

## Quick start
1. Copy `.env.example` → `.env` and fill values (IDs, paths, tokens).
2. Adjust `DOCKERCONFDIR` and `DOCKERSTORAGEDIR` to your host.
3. Launch:
```bash
docker compose up -d
```
