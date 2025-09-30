# AdGuard Home (DNS-level Ad/Tracker Blocking)

A network-wide DNS sinkhole with an easy web UI. This setup is sanitized and designed for a homelab running other services like Nginx Proxy Manager and Cloudflare Tunnel.

## Features
- DNS-level blocking of ads, trackers, malware
- Per-client rules, allow/block lists, query logs
- Optional DHCP server (replace your router's DHCP)
- Works behind Nginx Proxy Manager if you want remote UI

## Files
- `docker-compose.yml` — container definition
- `.env.example` — ports & timezone
- `config/`, `work/` — created on first run

## Quick Start
```bash
cp .env.example .env
docker compose up -d
```
Access the first-run wizard at:
- `http://<your-host>:${ADGUARD_SETUP_PORT:-3000}`

After the wizard completes, the UI moves to port 80 in the container. We map that to 8081 on the host, so visit:
- `http://<your-host>:${ADGUARD_UI_PORT:-8081}`

> If port 53 is in use, change `ADGUARD_DNS_PORT` in `.env` (e.g., `5353`) and point clients to that port, or stop the conflicting DNS service. For full compatibility (DHCP, mDNS, etc.), you can switch to host networking (see comments in compose).

## Router / Client Setup
- Set your LAN DNS to point to your AdGuard Home host IP (and port if not 53).
- Or set DNS per-device to test before cutting over the whole network.

## Upstream DNS
In AdGuard Home UI → Settings → DNS set upstreams, e.g.:
```
1.1.1.1
1.0.0.1
8.8.8.8
```
(You can also use DoH/DoT upstreams or a local recursive resolver.)

## Reverse Proxy (optional)
If you want to reach the UI via a domain:
- Nginx Proxy Manager → Proxy Host → `http://<adguard-host>:8081`
- Add an Access List / Auth as needed
- If exposing publicly, restrict by IP or require auth; consider Cloudflare Zero Trust.

## DHCP (optional)
Only enable AdGuard DHCP if your router’s DHCP is disabled. This will allow per-device naming and network-wide control, but it’s optional.

## Backups
- Export/Import settings from the UI (Settings → General → Backup)
- Snapshot the `config/` and `work/` volumes with your NAS backup (e.g., Backblaze B2).

## Security Notes
- Keep UI behind your reverse proxy and/or a private network/VPN.
- Use `no-new-privileges:true` (already in compose).
- Keep lists & the container updated.
