---
layout: page
title: Cloudflare + RTMP Secure Streaming
permalink: /cloudflare-rtmp/
---

# Cloudflare + RTMP Secure Streaming

## Goal
Enable a private, authenticated livestream (e.g., UAV/drone or event camera) with low maintenance.

## Tools Used
- nginx-rtmp (Docker)
- HLS output
- Cloudflare Tunnel (Zero Trust)

## Architecture
- Local RTMP ingest → nginx-rtmp → HLS segments
- Cloudflare Tunnel exposes the HLS endpoint privately (no inbound firewall rules)
- Access policy enforced via Zero Trust (per-user or per-team)

## Setup (High-Level)
1. Deploy `nginx-rtmp` via Docker.
2. Configure an application in Cloudflare Zero Trust and create a Tunnel to the host.
3. Route a subpath (e.g., `/stream`) or subdomain to the HLS output.
4. Apply an access policy (e.g., One-Time PIN, email domain) — no external IDP required.

> Avoid publishing internal domains or hostnames. Use placeholders like `stream.example.tld`.
