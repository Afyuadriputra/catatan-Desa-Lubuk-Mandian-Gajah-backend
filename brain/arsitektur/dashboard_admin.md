---
title: dashboard_admin
tags:
  - backend
  - django
  - feature
  - dashboard
  - admin
type: architecture_node
aliases:
  - Dashboard Admin
---

# dashboard_admin

> [!abstract]
> Feature agregasi operasional untuk admin desa. Bukan modul CRUD. Mengambil data dari feature lain untuk membentuk summary, queue, alert, analytics, health, dan activity feed.

## Komponen utama

- [[dashboard_admin_domain.py|domain.py]]
- [[dashboard_admin_repositories.py|repositories.py]]
- [[dashboard_admin_services.py|services.py]]
- [[dashboard_admin_schemas.py|schemas.py]]
- [[dashboard_admin_api.py|api.py]]
- [[dashboard_admin_permissions.py|permissions.py]]
- [[dashboard_admin_admin.py|admin.py]]
- [[dashboard_admin_apps.py|apps.py]]

## Blok data utama

- `overview`
- `surat_queue`
- `pengaduan_queue`
- `recent_activity`
- `surat_analytics`
- `pengaduan_analytics`
- `content_health`
- `master_health`

## Fitur operasional yang sudah aktif

- summary operasional surat / pengaduan / warga / unit published
- queue surat dan pengaduan dengan filter `scope/status/aging`
- recent activity:
  - surat
  - pengaduan
  - publikasi
  - auth
  - homepage
- analytics surat:
  - by status
  - by jenis
  - trend
  - average completion
  - missing nomor / PDF
  - rejection reasons
- analytics pengaduan:
  - by status
  - by kategori
  - trend
  - average first response
  - average resolved
  - oldest active
- content health:
  - draft publikasi
  - unpublished unit
  - unpublished perangkat
  - homepage completeness
  - important missing homepage sections
- master health:
  - dusun
  - perangkat
  - profile completeness
  - user active/inactive
  - role counts
- quick actions:
  - surat pending
  - pengaduan aktif
  - buat publikasi
  - kelola homepage
  - tambah dusun
  - tambah perangkat
  - kelola unit usaha

## Karakter arsitektur

- consume data dari modul lain
- pakai `django.core.cache`
- SLA operasional:
  - warning `>= 24 jam`
  - overdue `>= 72 jam`
- endpoint khusus admin via `AuthAdminOnly`

## Dependensi data

- [[layanan_administrasi]]
- [[pengaduan_warga]]
- [[publikasi_informasi]]
- [[potensi_ekonomi]]
- [[profil_wilayah]]
- [[auth_warga]]
- [[homepage_konten]]

## Catatan

> [!warning]
> Ini adalah dashboard operasional MVP+, belum analytics phase 2 penuh.
