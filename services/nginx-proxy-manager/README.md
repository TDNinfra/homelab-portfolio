# Nginx Proxy Manager

## What it is
[Nginx Proxy Manager](https://nginxproxymanager.com/) provides a simple web-based interface
to configure Nginx reverse proxy hosts with SSL certificates.

## Why I use it
To easily manage reverse proxies for self-hosted apps with Let's Encrypt integration and minimal manual Nginx config.

## How it integrates
- Runs on Synology's external `synobridge` network so it can reach other containers.
- Stores persistent config in `/data` and certificates in `/etc/letsencrypt`.
- Web UI exposed on `${ADMIN_PORT}` (default 81).

## Key config
- `PUID`/`PGID` → match host user/group IDs for file permissions.
- Ports mapped via `.env` so you can avoid conflicts with other services.
- Supports custom DB backends (MySQL/MariaDB) if needed, defaults to SQLite.

## Security
- Expose ports only as needed; run behind Cloudflare Tunnel if possible.
- Secure the admin interface with a strong password.
- Back up `/data` and `/etc/letsencrypt` volumes regularly.

## Quick start
1. Copy `.env.example` → `.env` and set values (UID/GID, ports, paths).
2. Ensure external Docker network `synobridge` exists:
```bash
docker network create synobridge
```
3. Launch:
```bash
docker compose up -d
```
