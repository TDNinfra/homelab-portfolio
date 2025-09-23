# Watchtower

## What it is
Watchtower monitors running Docker containers and automatically updates them when new images are available.

## Why I use it
Keeps services current without manual `docker pull` + restart cycles.

## How it integrates
- Mounts `/var/run/docker.sock` to talk to the Docker daemon.
- Runs on a cron schedule (default here: daily at 02:00).
- Updates running and stopped containers; avoids reviving intentionally stopped ones.

## Key config
- `WATCHTOWER_CLEANUP=true` → removes old images to reclaim disk.
- `WATCHTOWER_INCLUDE_STOPPED=true` → includes stopped containers in updates.
- `WATCHTOWER_REVIVE_STOPPED=false` → won't start containers that are intentionally stopped.
- `WATCHTOWER_SCHEDULE=0 0 2 * * *` → cron format.

## Security
- Has broad access via Docker socket—do not expose to the network.
- Use only trusted images; review updates periodically.

## Quick start
1. Copy `.env.example` → `.env` and set your timezone.
2. Launch:
```bash
docker compose up -d
```
