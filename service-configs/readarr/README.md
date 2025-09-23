# Readarr

## What it is
Readarr automates ebook/audiobook acquisition and management.

## Why I use it
To maintain a clean library of books with metadata and consistent naming.

## How it integrates in my stack
- Integrates with download clients and Prowlarr.
- Shares `/data` with Plex/metadata tools.

## Key features / config choices
- Same PUID/PGID pattern for permissions.
- Dedicated `/config` volume.

## Security & backup
- Keep provider credentials private.
- Include in backup plan.

## Ports
- 8787/tcp → Web UI

## Quick start
1. Copy `.env.example` → `.env` and fill values (IDs, paths, tokens).
2. Adjust `DOCKERCONFDIR` and `DOCKERSTORAGEDIR` to your host.
3. Launch:
```bash
docker compose up -d
```
