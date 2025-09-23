# Tautulli

## What it is
Tautulli monitors Plex activity and provides usage stats and notifications.

## Why I use it
For insights into server performance, streams, and to troubleshoot buffering.

## How it integrates in my stack
- Talks to Plex via API; optional notifications via webhooks.
- `/config` volume for persistence.

## Key features / config choices
- Debug disabled by default; enable only when needed.
- Logging limited to keep disk usage small.

## Security & backup
- Keep any webhook URLs out of git.
- Include Tautulli config in regular backups.

## Ports
- 8181/tcp → Web UI

## Quick start
1. Copy `.env.example` → `.env` and fill values (IDs, paths, tokens).
2. Adjust `DOCKERCONFDIR` and `DOCKERSTORAGEDIR` to your host.
3. Launch:
```bash
docker compose up -d
```
