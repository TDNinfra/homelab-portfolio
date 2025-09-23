# Bazarr

## What it is
Bazarr manages subtitles for Radarr/Sonarr libraries.

## Why I use it
To automatically fetch and maintain subtitles across languages.

## How it integrates in my stack
- Reads media paths via `/data/media` and updates subtitle files.
- Connects to Radarr/Sonarr over LAN or reverse proxy.

## Key features / config choices
- Runs with least privileges via PUID/PGID.
- Logs capped for disk hygiene.

## Security & backup
- Keep API keys in UI/env; do not publish provider credentials.
- Include `/config` in backups.

## Ports
- 6767/tcp → Web UI

## Quick start
1. Copy `.env.example` → `.env` and fill values (IDs, paths, tokens).
2. Adjust `DOCKERCONFDIR` and `DOCKERSTORAGEDIR` to your host.
3. Launch:
```bash
docker compose up -d
```
