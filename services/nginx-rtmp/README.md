# nginx-rtmp (RTMP ingest + HLS)

## What it is
Nginx with the RTMP module for live ingest (`rtmp://`) and HLS playback over HTTP.

## Why I use it
To stream a private live video (e.g., camera/drone) and serve it behind **Cloudflare Tunnel** with authentication.

## Quick start
1) Copy `.env.example` → `.env` and adjust ports/paths.
2) Edit `nginx.conf` as needed (HLS options, auth hooks).
3) Start:
```bash
docker compose up -d
```
4) Push RTMP from your encoder to: `rtmp://HOST:RTMP_PORT/live/STREAM_KEY`  
   - Playback HLS at: `http://HOST:HTTP_PORT/STREAM_KEY.m3u8`

## Security
- Put this behind Cloudflare Tunnel or a reverse proxy with auth.
- Consider signed URLs or auth hooks for RTMP/HLS if exposing beyond LAN.
