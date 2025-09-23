# cloudflared (Cloudflare Tunnel)

## What it is
A lightweight connector that creates an outbound-only, encrypted tunnel from your host to Cloudflare.

## Why I use it
To expose internal services securely without opening inbound firewall ports, and to layer **Cloudflare Zero Trust** auth in front.

## Modes
- **Token mode (recommended for simplicity):** set `TUNNEL_TOKEN` and run.
- **Named tunnel:** mount `/etc/cloudflared` with `cert.pem` + `config.yml` and run `tunnel run` or `tunnel --config ...`.

## Quick start
1) Copy `.env.example` → `.env` and set `TUNNEL_TOKEN` (or prepare named tunnel files).
2) Start:
```bash
docker compose up -d
```
3) In Cloudflare Zero Trust, add **Access policies** for your apps.

## Security
- Never commit tokens or certs.
- Use per-app policies (One-time PIN, email domain, or IdP).
