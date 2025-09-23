# SABnzbd

## What it is
SABnzbd is a Usenet binary newsreader and downloader with a web UI.

## Why I use it
To automate and manage Usenet downloads as part of a self-hosted media stack (Radarr, Sonarr, Lidarr).

## How it integrates
- Radarr/Sonarr send NZBs to SABnzbd.
- Downloads to `/usenet/incomplete` then moves to `/usenet/complete` when done.
- `/nzbs` can be used for watched folders.

## Key config
- `PUID`/`PGID` → ensures proper file permissions on downloads.
- `TZ` → timezone for logs/schedules.
- Exposes port `${HTTP_PORT}` mapped to internal `8080`.

## Security
- Run behind reverse proxy or Cloudflare Tunnel if exposing externally.
- Store credentials inside the SABnzbd UI (not in compose).

## Quick start
1. Copy `.env.example` → `.env` and set values (UID/GID, TZ, ports, paths).
2. Launch:
```bash
docker compose up -d
```
