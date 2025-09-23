---
layout: page
title: Backblaze NAS Backup
permalink: /backblaze-nas-backup/
---

# Backblaze B2 NAS Backup

## Goal
Add off-site redundancy and disaster recovery for NAS data and critical configs.

## Tools Used
- Backblaze B2
- NAS backup tool (e.g., Hyper Backup or rclone)

## Setup (Summary)
1. Create a B2 bucket and application key (store securely).
2. Connect NAS backup tool to B2 using the key ID & application key (do not publish these).
3. Choose source folders: media metadata, container configs, photos, documents.
4. Enable versioning and schedule nightly backups.
5. Test restore for a small subset regularly.

## Outcome
Resilient backups with versioning and off-site protection against hardware failure or local incidents.
