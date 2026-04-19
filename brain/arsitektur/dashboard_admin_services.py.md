---
title: dashboard_admin services.py
tags:
  - backend
  - django
  - service
  - dashboard
type: architecture_leaf
aliases:
  - dashboard_admin/services.py
---

# services.py

Modul: [[dashboard_admin]]
Layer: Service

## Use case utama

- `get_overview`
- `get_surat_queue`
- `get_pengaduan_queue`
- `get_recent_activity`
- `get_surat_analytics`
- `get_pengaduan_analytics`
- `get_content_health`
- `get_master_health`

## Catatan

- service ini adalah orchestrator utama dashboard
- sudah cukup besar, tapi masih source of truth agregasi operasional admin saat ini
