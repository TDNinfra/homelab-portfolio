---
title: IT & Homelab Portfolio
description: Real-world DevOps/sysadmin projects
layout: default
---

{% include header.html %}

# IT & Homelab Portfolio

Hi! I’m showcasing hands-on homelab & DevOps work: Dockerized services, reverse proxying, secure access, backups, and media workflow automation.

- **GitHub:** [TDNinfra](https://github.com/TDNinfra)
- **This site’s repo:** [/homelab-portfolio](https://github.com/TDNinfra/homelab-portfolio)

## Highlights
- Containerized media stack (*Radarr, Sonarr, Prowlarr, SABnzbd/qBittorrent, Plex, Tautulli, Bazarr, Overseerr*)
- Zero-trust access via **Cloudflare Tunnel**
- Reverse proxy & TLS with **Nginx Proxy Manager**
- **Vaultwarden** password manager
- **Immich** (self-hosted photos) with Postgres/Redis
- Scheduled updates: **Watchtower**, post-download **Unpackerr**
- Config drift control: **Recyclarr**
- Homelab **Homepage** dashboard
- **AdGuard Home** (DNS-level ad/tracker blocking with optional DHCP & proxy integration)
---

## Projects
See detailed configs, `.env.example` files, and READMEs for each service on the **Projects** page.

👉 **[Browse all services →]({{ site.baseurl }}/services/)**

> All examples are sanitized: no personal names, IPs, tokens, or secrets.

{% include footer.html %}
