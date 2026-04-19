---
architecture_node: '[[potensi_ekonomi]]'
status: linked_to_code
---

# Modul Potensi Ekonomi

Tags: #feature #bumdes #wisata

Etalase unit usaha desa dan wisata dalam satu model/domain operasional.

## Scope

- Dashboard usaha desa
- Katalog koperasi
- Katalog wisata
- Upload foto
- Kontak
- Harga tiket
- Fasilitas

## Entity utama

- `BumdesUnitUsaha`

Lihat: [[08 - Database Schema]]

## Kategori

- `KOPERASI`
- `WISATA`
- `JASA`

## Endpoint aktual

- `GET /api/v1/potensi-ekonomi/katalog`
- `GET /api/v1/potensi-ekonomi/{unit_id}`
- `GET /api/v1/potensi-ekonomi/admin/list`
- `POST /api/v1/potensi-ekonomi/admin/buat`
- `PUT /api/v1/potensi-ekonomi/admin/{unit_id}`
- `DELETE /api/v1/potensi-ekonomi/admin/{unit_id}`

## Aktor

- Admin BUMDes
- Warga

## Relasi

- Role akses dari [[02 - Modul Auth Warga]]
- Publik tampil bersama [[04 - Modul Publikasi Informasi]]

## Aturan bisnis

- Hanya Super Admin, Admin Desa, Admin BUMDes bisa kelola
- Hanya data `aktif/publish` tampil ke publik
- Upload gambar divalidasi
- Konten deskripsi/fasilitas disanitasi

## Status implementasi

> [!success]
> CRUD admin, katalog publik, publish/unpublish, validasi upload, sanitasi konten sudah aktif.
