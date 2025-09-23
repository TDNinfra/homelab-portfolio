# Plex Meta Manager

## What it is
[Plex Meta Manager](https://github.com/meisnate12/Plex-Meta-Manager) (PMM) is a tool to
automatically manage and update Plex library metadata (collections, posters, overlays, etc.)
using YAML configuration files.

## Why I use it
To enrich my Plex library with smart collections, poster art, and metadata synced from sources
like IMDb, TMDb, and Trakt without manual editing.

## How it integrates
- Mounts `/config` folder to hold YAML config files and logs.
- Connects to Plex server via API token (stored in YAML, not compose).
- Scheduled to run daily at `${PMM_TIME}`.

## Key config
- `PUID`/`PGID` → set to host user/group for permissions.
- `TZ` → timezone for logs.
- `PMM_TIME` → daily run time, e.g. `07:00`.

## Security
- Keep Plex token and API keys inside config YAML, never in git.
- Only grant container access to Plex server and required APIs.

## Quick start
1. Copy `.env.example` → `.env` and set values (UID/GID, TZ, run time).
2. Place your YAML config in `${DOCKERCONFDIR}/plex-meta-manager`.
3. Launch:
```bash
docker compose up -d
```
