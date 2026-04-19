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

Ringkasan endpoint backend. Dibagi dua: endpoint aktual vs endpoint target.

## Auth: endpoint aktual

- `POST /api/auth/login/`
- `POST /api/auth/logout/`
- `GET /api/auth/me/`
- `POST /api/auth/users/warga/create/`
- `POST /api/auth/users/admin/create/`
- `POST /api/auth/users/{user_id}/activate/`
- `POST /api/auth/users/{user_id}/deactivate/`

## Auth: endpoint target berikutnya

- `POST /api/auth/change-password/`
- `GET /api/auth/users/`
- `GET /api/auth/users/{id}/`

## Prefix route modul yang sudah diregistrasi

- `/api/auth/`
- `/api/layanan-administrasi/`
- `/api/pengaduan/`
- `/api/potensi-ekonomi/`
- `/api/profil-wilayah/`
- `/api/publikasi/`

## Modul lain

Saat ini route modul lain sudah di-include di `core_django.urls`, tapi mayoritas fitur masih scaffold. Jadi daftar endpoint detail di bawah ini masih status target desain.

## Profil Wilayah: target

- `GET /api/profil-wilayah/dusun/`
- `POST /api/profil-wilayah/dusun/`
- `GET /api/profil-wilayah/perangkat/`
- `POST /api/profil-wilayah/perangkat/`
- `GET /api/profil-wilayah/profil-desa/`
- `PUT /api/profil-wilayah/profil-desa/`

## Publikasi: target

- `GET /api/publikasi/berita/`
- `GET /api/publikasi/berita/{id}/`
- `POST /api/publikasi/berita/`
- `PUT /api/publikasi/berita/{id}/`
- `DELETE /api/publikasi/berita/{id}/`
- `GET /api/publikasi/pengumuman/`
- `GET /api/publikasi/pengumuman/{id}/`
- `POST /api/publikasi/pengumuman/`
- `PUT /api/publikasi/pengumuman/{id}/`
- `DELETE /api/publikasi/pengumuman/{id}/`

## Potensi Ekonomi: target

- `GET /api/potensi-ekonomi/unit-usaha/`
- `GET /api/potensi-ekonomi/unit-usaha/{id}/`
- `POST /api/potensi-ekonomi/unit-usaha/`
- `PUT /api/potensi-ekonomi/unit-usaha/{id}/`
- `DELETE /api/potensi-ekonomi/unit-usaha/{id}/`

## Layanan Administrasi: target

- `POST /api/layanan-administrasi/surat/`
- `GET /api/layanan-administrasi/surat/`
- `GET /api/layanan-administrasi/surat/{id}/`
- `PATCH /api/layanan-administrasi/surat/{id}/status/`
- `GET /api/layanan-administrasi/surat/{id}/pdf/`
- `GET /api/layanan-administrasi/surat/{id}/history/`

## Pengaduan: target

- `POST /api/pengaduan/`
- `GET /api/pengaduan/`
- `GET /api/pengaduan/{id}/`
- `PATCH /api/pengaduan/{id}/status/`
- `GET /api/pengaduan/{id}/history/`

## Catatan

- Endpoint admin dan publik perlu pisah permission
- Implementasi sekarang pakai Django view + `JsonResponse`, belum Django Ninja
- Kalau nanti pindah ke Django Ninja, note ini perlu revisi lagi
- Semua endpoint kembali ke modul:
  - [[02 - Modul Auth Warga]]
  - [[03 - Modul Profil Wilayah]]
  - [[04 - Modul Publikasi Informasi]]
  - [[05 - Modul Potensi Ekonomi]]
  - [[06 - Modul Layanan Administrasi]]
  - [[07 - Modul Pengaduan Warga]]
