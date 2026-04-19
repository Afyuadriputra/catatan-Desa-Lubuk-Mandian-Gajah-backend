---
architecture_node: '[[potensi_ekonomi]]'
status: linked_to_code
---

# Modul Potensi Ekonomi

Tags: #feature #bumdes #wisata

Etalase usaha desa, koperasi, wisata.

## Scope

- Dashboard usaha desa
- Katalog koperasi
- Katalog wisata
- Upload foto
- Kontak
- Harga tiket
- Fasilitas

## Entity utama

- `UnitUsaha`
- `Wisata` atau `UnitUsaha` dengan kategori

Lihat: [[08 - Database Schema]]

## Kategori

- `KOPERASI`
- `WISATA`
- `JASA`

## Endpoint kandidat

- `GET /api/unit-usaha`
- `GET /api/unit-usaha/{id}`
- `POST /api/unit-usaha`
- `PUT /api/unit-usaha/{id}`
- `DELETE /api/unit-usaha/{id}`

## Aktor

- Admin BUMDes
- Warga

## Relasi

- Role akses dari [[02 - Modul Auth Warga]]
- Publik tampil bersama [[04 - Modul Publikasi Informasi]]

## Aturan bisnis

- Hanya Super Admin, Admin Desa, Admin BUMDes bisa kelola
- Hanya data `aktif/publish` tampil ke publik