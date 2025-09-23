# Qbittorrent

## Quick start
1) Copy `.env.example` to `.env` and set values.
2) Adjust `DOCKERCONFDIR`/`DOCKERSTORAGEDIR` to your host paths.
3) Start:
```bash
docker compose up -d
```

## Ports
- 8080/tcp → Web UI
- 8118/tcp → Privoxy (optional)

## Notes
- Do **not** commit your real `.env`.
- If using VPN, uncomment /dev/net/tun and set provider.
