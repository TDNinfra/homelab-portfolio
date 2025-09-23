# Vaultwarden

## What it is
Vaultwarden is a lightweight, self-hosted password manager compatible with Bitwarden clients.

## Why I use it
To self-host my credentials and secrets while keeping control over access, updates, and backups.

## How it integrates
- Runs on port 8080 internally, mapped to ${HTTP_PORT} externally.
- Data is stored in `${DOCKERCONFDIR}/vaultwarden`.
- Admin interface secured with an Argon2-hashed `ADMIN_TOKEN`.
- Network mode set to bridge by default; adjust if using Synology custom networks.

## Key config
- `ROCKET_ENV=staging` → optimized for production use.
- `ROCKET_PORT=8080` → internal port.
- `ROCKET_WORKERS=10` → worker threads for handling requests.
- `SIGNUPS_ALLOWED=false` → disables open registration.
- `ADMIN_TOKEN` → long, secure Argon2id hash for the admin panel.

## Security
- Do **not** expose Vaultwarden directly; put behind Cloudflare Tunnel or a reverse proxy with TLS & auth.
- Disable signups once your account is created.
- Back up the `/data` volume regularly, encrypt off-site copies.

## Quick start
1. Copy `.env.example` → `.env` and set values.
2. Adjust volumes and network mode if on Synology or other host.
3. Launch:
```bash
docker compose up -d
```
