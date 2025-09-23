# qBittorrent

## What it is
qBittorrent is a BitTorrent client with a web UI and categories/labels.

## Why I use it
To support torrent workflows when needed, alongside Usenet.

## How it integrates in my stack
- Exposes optional Privoxy; integrates with Radarr/Sonarr via category paths.
- Optional VPN support via WireGuard device and provider config.

## Key features / config choices
- Ports set via env for easy changes.
- IPv6 disabled by default to simplify routing.

## Security & backup
- Do not publish torrent trackers or VPN configs.
- Back up `/config`.

## Ports
- 8080/tcp → Web UI
- 8118/tcp → Privoxy (optional)

## Quick start
1. Copy `.env.example` → `.env` and fill values (IDs, paths, tokens).
2. Adjust `DOCKERCONFDIR` and `DOCKERSTORAGEDIR` to your host.
3. Launch:
```bash
docker compose up -d
```
