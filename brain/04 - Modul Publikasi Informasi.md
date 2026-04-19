---
architecture_node: '[[publikasi_informasi]]'
status: linked_to_code
---

# Modul Publikasi Informasi

Tags: #feature #cms #publikasi

CMS berita dan pengumuman.

## Scope

- Berita desa
- Pengumuman
- Rich text editor
- Sanitasi anti-XSS

## Entity utama

- `Berita`
- `Pengumuman`

Lihat: [[08 - Database Schema]]

## Status

- `DRAFT`
- `PUBLISHED`

## Endpoint kandidat

- `GET /api/berita`
- `GET /api/berita/{id}`
- `POST /api/berita`
- `PUT /api/berita/{id}`
- `DELETE /api/berita/{id}`
- `GET /api/pengumuman`
- `GET /api/pengumuman/{id}`
- `POST /api/pengumuman`
- `PUT /api/pengumuman/{id}`
- `DELETE /api/pengumuman/{id}`

## Dependensi

- Sanitizer HTML
- Audit log
- Penulis dari [[02 - Modul Auth Warga]]

## Aturan bisnis

- Konten `DRAFT` tidak tampil publik
- Hanya Admin Desa dan Super Admin bisa publish
- HTML harus disanitasi saat simpan

## Catatan model

- Perlu `slug`
- Perlu `published_at`
- Bisa pecah model `Berita` dan `Pengumuman`, atau generic `Post` dengan tipe konten