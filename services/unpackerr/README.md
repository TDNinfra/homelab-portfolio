# Unpackerr

## What it is
Unpackerr watches download clients (like SABnzbd, qBittorrent, NZBGet, etc.) and automatically extracts compressed files after download.

## Why I use it
To automate unpacking of archives (RAR, ZIP) that come from Usenet/torrent downloads, so Radarr/Sonarr can import them cleanly into the media library.

## How it integrates
- Monitors configured download clients through their APIs.
- Extracts completed downloads in `/data`.
- Keeps a `/config` folder for settings and logs.

## Key config
- `PUID`/`PGID` → match host user/group for permissions.
- `TZ` → timezone setting for logs/schedules.
- `UMASK=002` → controls default file permissions.

## Security
- Runs with `no-new-privileges` for hardening.
- Only has access to the directories you explicitly mount (`/data` and `/config`).

## Quick start
1. Copy `.env.example` → `.env` and set values (UID/GID, timezone, paths).
2. Launch:
```bash
docker compose up -d
```
