---
title: dashboard_admin repositories.py
tags:
  - backend
  - django
  - repository
  - dashboard
type: architecture_leaf
aliases:
  - dashboard_admin/repositories.py
---

# repositories.py

Modul: [[dashboard_admin]]
Layer: Repository

## Tanggung jawab

- summary metrics
- query queue surat/pengaduan
- trend 7 hari
- statistik by status/kategori/jenis
- recent activity source query
- content health query
- master health query

## Karakter query

- banyak agregasi ORM
- memakai `Count`, `Min`, `Q`, `TruncDate`
- `select_related` untuk queue/activity
