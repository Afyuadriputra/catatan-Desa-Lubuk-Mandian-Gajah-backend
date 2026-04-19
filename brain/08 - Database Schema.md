# Database Schema

Tags: #database #erd #postgresql

Skema inti dari [[00 - PRD Desa Mandian Gajah]].

## Tabel utama

- `users_customuser`
- `wilayah_dusun`
- `wilayah_perangkat`
- `publikasi_berita`
- `publikasi_pengumuman` atau `publikasi_post`
- `bumdes_unit_usaha`
- `layanan_surat`
- `layanan_surat_status_history`
- `layanan_pengaduan`
- `layanan_pengaduan_history`

## Relasi inti

- `wilayah_perangkat.user_id` -> `users_customuser.id`
- `publikasi_berita.penulis_id` -> `users_customuser.id`
- `layanan_surat.pemohon_id` -> `users_customuser.id`
- `layanan_surat_status_history.surat_id` -> `layanan_surat.id`
- `layanan_surat_status_history.changed_by` -> `users_customuser.id`
- `layanan_pengaduan.pelapor_id` -> `users_customuser.id`
- `layanan_pengaduan_history.pengaduan_id` -> `layanan_pengaduan.id`
- `layanan_pengaduan_history.changed_by` -> `users_customuser.id`

## Modul terkait

- [[02 - Modul Auth Warga]]
- [[03 - Modul Profil Wilayah]]
- [[04 - Modul Publikasi Informasi]]
- [[05 - Modul Potensi Ekonomi]]
- [[06 - Modul Layanan Administrasi]]
- [[07 - Modul Pengaduan Warga]]

## Catatan desain

- User pakai UUID
- `CustomUser`: `nik`, `nama_lengkap`, `nomor_hp`, `role`, `is_active`, timestamps
- `wilayah_perangkat`: perlu `is_published`
- `publikasi_berita`: perlu `slug`, `published_at`
- `bumdes_unit_usaha`: perlu `harga_tiket`, `is_published`
- `layanan_surat`: perlu `nomor_surat`, `pdf_url`, `rejection_reason`
- `layanan_pengaduan`: perlu `kategori`
- Tabel domain lain bisa pakai serial atau UUID, tapi bagus konsisten UUID kalau mau scale
- Enum status sebaiknya pakai `TextChoices`
- Index wajib pada `nik`, status, timestamp, FK penting
