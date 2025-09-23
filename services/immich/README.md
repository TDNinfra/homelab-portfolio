# Immich (photos & videos platform)

> **Important:** For installs/upgrades, always check the official guide and use the compose file from the latest release:
> https://immich.app/docs/install/docker-compose and the release compose at:
> https://github.com/immich-app/immich/releases/latest/download/docker-compose.yml

## What it is
Immich is a self‑hosted photo & video platform with fast mobile upload and on‑device/server ML (face/object search).

## Why I use it
To keep my photo library private while retaining the speed and discovery features of commercial cloud services.

## Services in this compose
- `immich-server` — web/API on **2283**
- `immich-machine-learning` — ML workers (can use GPU with accel tags)
- `redis` — lightweight cache/queue (Valkey)
- `database` — Postgres with vector extension

## Hardware acceleration
- For transcoding or ML acceleration, append a tag to the images (e.g., `${IMMICH_VERSION}-cuda`) and follow the Immich docs for the matching `hwaccel.*.yml` include.

## Volumes & data
- **Uploads**: `${UPLOAD_LOCATION}:/data`
- **Postgres data**: `${DB_DATA_LOCATION}:/var/lib/postgresql/data`
- **ML cache**: `model-cache:/cache`

## Security & backup
- Place behind a reverse proxy (Cloudflare Tunnel or Nginx Proxy Manager) with TLS and auth.
- Back up:
  - the upload path (`${UPLOAD_LOCATION}`)
  - Postgres data (`${DB_DATA_LOCATION}`)
- Rotate DB creds if exposed. Keep `.env` out of git.

## Quick start
1. Copy `.env.example` → `.env` and fill values (paths, DB creds).
2. Create host directories for upload and DB data.
3. Launch:
```bash
docker compose up -d
```
4. Access Immich at: `http://HOST:2283/`
