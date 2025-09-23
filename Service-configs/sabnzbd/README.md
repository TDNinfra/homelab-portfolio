# Sabnzbd

## Quick start
1) Copy `.env.example` to `.env` and set values.
2) Adjust `DOCKERCONFDIR`/`DOCKERSTORAGEDIR` to your host paths.
3) Start:
```bash
docker compose up -d
```

## Ports
- 7080/tcp → Web UI
- 9090/tcp → Optional HTTPS/API

## Notes
- Do **not** commit your real `.env`.
