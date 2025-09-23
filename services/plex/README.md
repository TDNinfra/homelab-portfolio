# Plex

## What it is
Plex is a media server for streaming your library to clients.

## Why I use it
To serve a curated, high-quality media library to home devices.

## How it integrates in my stack
- Shares `/data/media` volume with the rest of the stack.
- Hardware transcoding enabled via `/dev/dri` (requires Plex Pass).

## Key features / config choices
- Claim token is provided at first run.
- `ADVERTISE_IP` ensures clients can find the server on LAN/VPN.

## Security & backup
- Never publish claim token.
- Back up `/config` and metadata; thumbnails can be regenerated.

## Ports
- 32400/tcp → Web UI + clients

## Quick start
1. Copy `.env.example` → `.env` and fill values (IDs, paths, tokens).
2. Adjust `DOCKERCONFDIR` and `DOCKERSTORAGEDIR` to your host.
3. Launch:
```bash
docker compose up -d
```
