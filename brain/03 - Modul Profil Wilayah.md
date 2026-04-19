---
architecture_node: '[[profil_wilayah]]'
status: linked_to_code
---

# Modul Profil Wilayah

Tags: #feature #profil #wilayah

Modul data desa untuk [[00 - PRD Desa Mandian Gajah]].

## Scope

- CRUD dusun
- Struktur organisasi desa
- Halaman visi, misi, sejarah
- Upload foto perangkat desa

## Entity utama

- `Dusun`
- `PerangkatDesa`

Lihat: [[08 - Database Schema]]

## Endpoint kandidat

- `GET /api/dusun`
- `POST /api/dusun`
- `GET /api/perangkat`
- `POST /api/perangkat`
- `GET /api/profil-desa`
- `PUT /api/profil-desa`

## Relasi

- `PerangkatDesa` -> `CustomUser`
- Admin kelola konten publik desa
- Hanya data perangkat `aktif/publish` tampil ke publik

Lihat:

- [[02 - Modul Auth Warga]]
- [[09 - API Endpoint Plan]]
- [[11 - Access Matrix]]