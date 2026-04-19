# PRD Desa Mandian Gajah

Tags: #prd #smart-village #backend

PRD revisi `v1.2.0`. Note pusat untuk turunan PRD backend.

## Tujuan

- Digitalisasi administrasi desa
- Percepat pelayanan surat ke hari kerja sama / menit
- Sistem kerja perangkat desa lebih rapi
- Transparansi publik
- Promosi BUMDes dan wisata
- Fondasi backend aman dan scalable

## Metrik

- 80% surat diproses di hari kerja sama
- 90% berita/pengumuman bisa dipublish tanpa bantuan teknis
- 70% pengaduan dapat respons awal < 1x24 jam kerja
- 95% data dusun dan perangkat berhasil dimigrasikan
- P95 endpoint baca < 300 ms
- Uptime bulanan >= 99.5%

## Turunan

- [[01 - Backend Architecture]]
- [[02 - Modul Auth Warga]]
- [[03 - Modul Profil Wilayah]]
- [[04 - Modul Publikasi Informasi]]
- [[05 - Modul Potensi Ekonomi]]
- [[06 - Modul Layanan Administrasi]]
- [[07 - Modul Pengaduan Warga]]
- [[08 - Database Schema]]
- [[09 - API Endpoint Plan]]
- [[10 - Backend Roadmap]]
- [[11 - Access Matrix]]
- [[12 - Non-Functional Requirements]]
- [[13 - User Flows]]

## Persona

- Super Admin
- Admin Desa
- Admin BUMDes
- Warga

## Scope

- MVP: auth, profil wilayah, publikasi, surat, pengaduan, BUMDes/wisata dasar
- Phase 2: notifikasi, QR surat, analitik, multi-template surat
- Out of scope MVP: Dukcapil, pembayaran online, mobile app native, multi-tenant
