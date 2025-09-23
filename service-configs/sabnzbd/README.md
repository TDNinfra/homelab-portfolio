# SABnzbd

## What it is
SABnzbd is a Usenet downloader with a web UI.

## Why I use it
To provide fast, automated Usenet downloads feeding Radarr/Sonarr.

## How it integrates in my stack
- Uses `/data/usenet` for incoming + completed downloads.
- Radarr/Sonarr pick up completed files via `/data`.

## Key features / config choices
- PUID/PGID ensure correct permissions on files.
- Ports exposed for UI and optional HTTPS/API.

## Security & backup
- Keep Usenet credentials in the UI, not in git.
- Back up `/config` regularly.

## Ports
- 7080/tcp → Web UI
- 9090/tcp → Optional HTTPS/API

## Quick start
1. Copy `.env.example` → `.env` and fill values (IDs, paths, tokens).
2. Adjust `DOCKERCONFDIR` and `DOCKERSTORAGEDIR` to your host.
3. Launch:
```bash
docker compose up -d
```
