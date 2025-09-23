---
layout: page
title: IT & Homelab Projects
---

<div class="hero">
  <h1>IT & Homelab Projects</h1>
  <p>Portfolio of practical projects covering Docker, Cloudflare Zero Trust, RTMP streaming, Plex automation, Immich, Home Assistant, and Backblaze B2 off-site backups.</p>
</div>

## Featured Projects

<div class="grid">
  {% include project-card.md
    title="Docker Stack Overview"
    href="docker-stack/"
    summary="Multi-service stack managed with Portainer and a simple dashboard."
    tags="Docker,Portainer,Operations" %}
  {% include project-card.md
    title="Cloudflare + RTMP Secure Streaming"
    href="cloudflare-rtmp/"
    summary="Private livestream using nginx-rtmp, HLS, and Cloudflare Zero Trust."
    tags="RTMP,HLS,Cloudflare,Security" %}
  {% include project-card.md
    title="Immich (Self-Hosted Photos)"
    href="immich-setup/"
    summary="AI-assisted photo library using Immich with Postgres and Redis."
    tags="Immich,AI,Postgres,Redis" %}
  {% include project-card.md
    title="Backblaze B2 NAS Backup"
    href="backblaze-nas-backup/"
    summary="Disaster recovery via NAS backups to Backblaze B2 with versioning."
    tags="Backups,B2,DR" %}
  {% include project-card.md
    title="Home Assistant + Smart Devices"
    href="home-assistant/"
    summary="Aqara and camera integrations with a wall-mounted dashboard."
    tags="IoT,Home Assistant,Automation" %}
  {% include project-card.md
    title="Plex Media & Automation Suite"
    href="plex-automation/"
    summary="Radarr/Prowlarr/Sabnzbd/Unpackerr/Bazarr/Kometa pipeline."
    tags="Plex,Automation,Usenet" %}
  {% include project-card.md
    title="Vaultwarden (Password Manager)"
    href="vaultwarden/"
    summary="Self-hosted password manager behind a Zero Trust tunnel."
    tags="Security,Passwords,Zero Trust" %}
</div>

---

### Notes on Privacy
This site omits personally identifying information (names, addresses, domains, IPs). Config snippets and screenshots should be redacted before publishing.
