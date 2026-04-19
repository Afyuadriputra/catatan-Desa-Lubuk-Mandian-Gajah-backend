---
title: dashboard_admin api.py
tags:
  - backend
  - django
  - api
  - dashboard
type: architecture_leaf
aliases:
  - dashboard_admin/api.py
---

# api.py

Modul: [[dashboard_admin]]
Layer: Presentation / API

## Endpoint aktif

- `GET /dashboard-admin/overview`
- `GET /dashboard-admin/surat-queue`
- `GET /dashboard-admin/pengaduan-queue`
- `GET /dashboard-admin/recent-activity`
- `GET /dashboard-admin/surat-analytics`
- `GET /dashboard-admin/pengaduan-analytics`
- `GET /dashboard-admin/content-health`
- `GET /dashboard-admin/master-health`

## Legacy compat

- `GET /dashboard-admin/analitik/`

## Kontrak

- `overview` mengembalikan blok:
  - `summary`
  - `alerts`
  - `charts`
  - `health`
  - `quick_actions`
