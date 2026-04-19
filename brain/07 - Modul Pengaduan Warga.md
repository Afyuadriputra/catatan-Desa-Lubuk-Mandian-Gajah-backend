---
architecture_node: '[[pengaduan_warga]]'
status: linked_to_code
---

# Modul Pengaduan Warga

Tags: #feature #pengaduan #ticketing

Modul laporan masalah warga.

## Scope

- Form pengaduan
- Upload foto bukti
- Kategori pengaduan
- Tracking status ticket
- Catatan admin
- Riwayat tindak lanjut

## Entity utama

- `Pengaduan`
- `PengaduanHistory`

Lihat: [[08 - Database Schema]]

## Status

- `OPEN`
- `TRIAGED`
- `IN_PROGRESS`
- `RESOLVED`
- `CLOSED`

## Endpoint kandidat

- `POST /api/pengaduan`
- `GET /api/pengaduan`
- `GET /api/pengaduan/{id}`
- `PATCH /api/pengaduan/{id}/status`
- `GET /api/pengaduan/{id}/history`

## Dependensi

- Pelapor dari [[02 - Modul Auth Warga]]
- Media storage
- Audit log

## Aturan bisnis

- Warga hanya lihat pengaduan milik sendiri
- Foto bukti opsional
- Kategori dan deskripsi minimum wajib
- Admin wajib beri catatan saat status `RESOLVED` atau `CLOSED`