# Radarr

## What it is
Radarr is a movie manager that automates acquisition and organization.

## Why I use it
To automatically add, download, and sort movies for Plex.

## How it integrates in my stack
- Indexers come via Prowlarr; downloads via SABnzbd/qBittorrent.
- `/data` shared with Plex for instant visibility.

## Key features / config choices
- PUID/PGID avoid permission issues.
- Clean separation of `/config` and `/data`.

## Security & backup
- No keys in compose; all secrets live in the app UI or `.env`.
- Back up Radarr config with the NAS.

## Ports
- 7878/tcp → Web UI

## Quick start
1. Copy `.env.example` → `.env` and fill values (IDs, paths, tokens).
2. Adjust `DOCKERCONFDIR` and `DOCKERSTORAGEDIR` to your host.
3. Launch:
```bash
docker compose up -d
```
