---
title: API Endpoint Plan
tags:
  - api
  - planning
  - backend
aliases:
  - Rencana Endpoint API
status: active
---

# API Endpoint Plan

Ringkasan endpoint backend. Fokus note ini sekarang: endpoint aktual utama yang benar-benar sudah hidup.

## Auth: endpoint aktual

- `POST /api/v1/auth/login`
- `POST /api/v1/auth/logout`
- `GET /api/v1/auth/me`
- `POST /api/v1/auth/change-password`
- `POST /api/v1/auth/users/warga/create`
- `POST /api/v1/auth/users/admin/create`
- `POST /api/v1/auth/users/{user_id}/activate`
- `POST /api/v1/auth/users/{user_id}/deactivate`

## Prefix route modul yang sudah diregistrasi

- `/api/v1/auth`
- `/api/v1/dashboard-admin`
- `/api/v1/homepage`
- `/api/v1/layanan-administrasi`
- `/api/v1/pengaduan`
- `/api/v1/potensi-ekonomi`
- `/api/v1/profil-wilayah`
- `/api/v1/publikasi`

## Homepage: endpoint aktual

- `GET /api/v1/homepage`
- `GET /api/v1/homepage/admin/content`
- `PUT /api/v1/homepage/admin/content`
- CRUD child item untuk:
  - `culture-cards`
  - `recovery-items`
  - `potential-opportunities`
  - `facilities`
  - `gallery`
  - `footer-links`

## Dashboard Admin: endpoint aktual

- `GET /api/v1/dashboard-admin/overview`
- `GET /api/v1/dashboard-admin/surat-queue`
- `GET /api/v1/dashboard-admin/pengaduan-queue`
- `GET /api/v1/dashboard-admin/recent-activity`
- `GET /api/v1/dashboard-admin/surat-analytics`
- `GET /api/v1/dashboard-admin/pengaduan-analytics`
- `GET /api/v1/dashboard-admin/content-health`
- `GET /api/v1/dashboard-admin/master-health`

## Modul inti lain: endpoint aktual ringkas

- Profil wilayah:
  - publik profil desa
  - CRUD dusun
  - CRUD perangkat
  - update profil desa
- Publikasi:
  - list/detail publik
  - create/update/delete admin
  - ubah status publish
- Layanan administrasi:
  - ajukan surat
  - list/detail surat
  - proses status
  - download PDF
- Pengaduan:
  - buat pengaduan
  - list/detail pengaduan
  - proses status
- Potensi ekonomi:
  - katalog/detail publik
  - list admin
  - create/update/delete admin

## Catatan

- Endpoint admin dan publik dipisah permission
- Implementasi aktual sudah pakai Django Ninja
- Semua endpoint kembali ke modul:
  - [[02 - Modul Auth Warga]]
  - [[03 - Modul Profil Wilayah]]
  - [[04 - Modul Publikasi Informasi]]
  - [[05 - Modul Potensi Ekonomi]]
  - [[06 - Modul Layanan Administrasi]]
  - [[07 - Modul Pengaduan Warga]]
  - [[16 - Modul Homepage Konten]]
