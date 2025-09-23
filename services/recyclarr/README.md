# Recyclarr

## What it is
[Recyclarr](https://recyclarr.dev/) syncs custom quality definitions and settings between your *arr applications (Radarr, Sonarr) and community-maintained presets.

## Why I use it
To keep Radarr and Sonarr configured with up-to-date quality profiles, release settings, and proper score tuning—without manual tweaking.

## How it integrates
- Mounts `/config` to store YAML files defining sync rules.
- Connects to Radarr/Sonarr APIs to push configuration.
- Runs inside an external Docker network called `recyclarr` for better service isolation.

## Key config
- `PUID`/`PGID` ensure correct file permissions.
- `TZ` sets timezone for logs and cron scheduling.
- External network `recyclarr` must exist (create with `docker network create recyclarr`).

## Security
- Keep API keys for Radarr/Sonarr inside config YAMLs, never in git.
- Only grant network access to services it needs to reach.

## Quick start
1. Copy `.env.example` → `.env` and set values (UID/GID, TZ, paths).
2. Ensure the Docker network exists:
```bash
docker network create recyclarr
```
3. Place your YAML config in `${DOCKERCONFDIR}/recyclarr`.
4. Launch:
```bash
docker compose up -d
```
