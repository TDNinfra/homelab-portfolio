---
layout: page
title: Immich Setup
permalink: /immich-setup/
---

# Immich Setup (Self-Hosted Photos)

## Goal
Self-host a private photo library with AI-powered search and tagging.

## Tools Used
- Immich (server + ML)
- Postgres
- Redis
- Docker Compose

## Setup (Summary)
1. Use the official Immich docker-compose template.
2. Map persistent volumes for Postgres, Redis, and Immich data.
3. Enable hardware acceleration if available (optional).
4. Configure backup jobs (see Backblaze page).

## Outcome
A private, searchable photo platform with face detection and clustering, eliminating reliance on third-party clouds.
