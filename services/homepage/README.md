# Homepage (self-hosted dashboard)

## What it is
[Homepage](https://gethomepage.dev/) is a modern, fast home dashboard to organize links, monitor services, and show widgets (Docker, system stats, etc.).

## Why I use it
To create a single-pane dashboard for my homelab: quick links to services, status widgets, search, and bookmarks.

## How it integrates
- Reads config from `/app/config` (mounted from `${DOCKERCONFDIR}/homepage/config`).
- Optionally reads Docker API via `/var/run/docker.sock` to auto-show container status.
- Web UI exposed on `${HTTP_PORT}` (defaults to 3000).

## Key config
- `PUID`/`PGID` → make sure they match your host user and group so it can read/write config files.
- Config files you’ll likely add:
  - `docker.yaml` — for Docker widgets
  - `services.yaml` — tiles/links to your apps
  - `bookmarks.yaml`, `widgets.yaml`, `settings.yaml` — optional

## Security
- If you don’t need Docker integration, remove the Docker socket mount.
- If exposed beyond LAN, put behind a reverse proxy with auth (e.g., Nginx Proxy Manager + Cloudflare Access).
- Keep config files (with internal URLs) private.

## Quick start
1. Copy `.env.example` → `.env` and set values (UID/GID, port, paths).
2. Create the config directory on the host:
```bash
mkdir -p ${DOCKERCONFDIR}/homepage/config
```
3. Launch:
```bash
docker compose up -d
```
4. Open `http://HOST:${HTTP_PORT}` and follow the docs to add your `*.yaml` files.

## Example minimal `services.yaml`
```yaml
- Media:
    - Plex:
        href: http://plex.local:32400/web
        icon: plex
    - Radarr:
        href: http://radarr.local:7878
        icon: radarr
    - Sonarr:
        href: http://sonarr.local:8989
        icon: sonarr
```
