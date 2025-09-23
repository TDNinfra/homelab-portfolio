---
layout: page
title: Plex Media & Automation Suite
permalink: /plex-automation/
---

# Plex Media & Automation Suite

## Goal
Automate acquisition, organization, and streaming of media with minimal manual steps.

## Tools Used
- Plex
- Radarr (and/or Sonarr), Prowlarr
- Sabnzbd (or qBittorrent)
- Unpackerr
- Bazarr
- Kometa (metadata/collections)

## Pipeline
1. Radarr/Sonarr discover and request content.
2. Prowlarr indexes and routes to downloader.
3. Sabnzbd/qBittorrent downloads.
4. Unpackerr extracts archives.
5. Bazarr fetches subtitles.
6. Kometa curates metadata & collections.
7. Plex serves content to clients.

> Respect your jurisdiction's laws and content licensing terms.
