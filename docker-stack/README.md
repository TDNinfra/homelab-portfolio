---
layout: page
title: Docker Stack Overview
permalink: /docker-stack/
---

# Docker Stack Overview

## Goal
Run multiple self-hosted services using Docker with simple management and monitoring.

## Tools Used
- Docker & Docker Compose
- Portainer-CE (UI)
- Homepage (dashboard)

## Setup (Summary)
1. Install Docker and Docker Compose on the host (NAS or Linux).
2. Deploy Portainer for GUI management.
3. Create a `docker-compose.yml` for core services.
4. Add a Homepage dashboard for quick links.

## Example (Redacted) docker-compose.yml
> **Note:** Replace image tags, volumes, and ports with your environment. Do not publish secrets.
```yaml
version: "3.8"
services:
  portainer:
    image: portainer/portainer-ce:latest
    ports: ["9443:9443"]
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - portainer_data:/data
    restart: unless-stopped

volumes:
  portainer_data: {}
```

## Outcome
A maintainable, modular homelab that runs 10–20+ containers for media, backups, automation, and more.
