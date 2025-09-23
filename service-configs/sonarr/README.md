# Sonarr

## What it is
Sonarr manages TV series acquisition and organization.

## Why I use it
To keep TV libraries up-to-date with minimal manual work.

## How it integrates in my stack
- Uses Prowlarr for indexers; SABnzbd/qBittorrent for downloads.
- Shares `/data` with Plex to expose completed media.

## Key features / config choices
- PUID/PGID set for permission consistency.
- Clean `/config` volume for backup.

## Security & backup
- No secrets in compose; configure inside the app.
- Back up `/config`.

## Ports
- 8989/tcp → Web UI

## Quick start
1. Copy `.env.example` → `.env` and fill values (IDs, paths, tokens).
2. Adjust `DOCKERCONFDIR` and `DOCKERSTORAGEDIR` to your host.
3. Launch:
```bash
docker compose up -d
```
