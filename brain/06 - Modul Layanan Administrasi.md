---
architecture_node: '[[layanan_administrasi]]'
status: linked_to_code
---

# Modul Layanan Administrasi

Tags: #feature #surat #pdf

Modul pelayanan surat otomatis.

## Scope

- Pengajuan surat
- Tracking status
- Review admin
- Generate PDF
- Alasan penolakan
- Unduh PDF saat selesai

## Jenis surat

- `SKU`
- `SKTM`
- `DOMISILI`

## Entity utama

- `Surat`
- `SuratStatusHistory`

Lihat: [[08 - Database Schema]]

## Status

- `PENDING`
- `VERIFIED`
- `PROCESSED`
- `DONE`
- `REJECTED`

## Endpoint kandidat

- `POST /api/surat`
- `GET /api/surat`
- `GET /api/surat/{id}`
- `PATCH /api/surat/{id}/status`
- `GET /api/surat/{id}/pdf`
- `GET /api/surat/{id}/history`

## Dependensi

- Pemohon dari [[02 - Modul Auth Warga]]
- PDF generator
- Storage file
- Audit log

## Flow ringkas

Warga ajukan -> admin verifikasi -> sistem generate PDF -> warga unduh.

## Aturan bisnis

- Warga hanya lihat surat milik sendiri
- Admin Desa dan Super Admin lihat semua surat
- `jenis_surat` dan `keperluan` wajib
- `REJECTED` wajib isi `rejection_reason`
- PDF final hanya tersedia saat `DONE`
- Dokumen final tidak boleh diubah tanpa log perubahan
- Setiap perubahan status simpan timestamp dan actor