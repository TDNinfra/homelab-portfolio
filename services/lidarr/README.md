# Lidarr

## What it is
Lidarr is an audio/music collection manager that automates downloads and organization.

## Why I use it
To maintain a clean, automated music library accessible from Plex.

## How it integrates in my stack
- Uses `/data` shared storage so completed downloads appear in Plex.
- Pulls indexers from Prowlarr.

## Key features / config choices
- PUID/PGID set for correct file ownership.
- Separate `/config` for easy backup/restore.

## Security & backup
- Redacted credentials stay out of git.
- Config included in NAS → Backblaze backup policy.

## Ports
- 8686/tcp → Web UI

## Quick start
1. Copy `.env.example` → `.env` and fill values (IDs, paths, tokens).
2. Adjust `DOCKERCONFDIR` and `DOCKERSTORAGEDIR` to your host.
3. Launch:
```bash
docker compose up -d
```
