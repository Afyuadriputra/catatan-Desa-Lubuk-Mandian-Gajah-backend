# Backend Roadmap

Tags: #roadmap #backend #implementation

Urutan bangun backend dari hasil mapping.

## Sprint 1

- Scaffold Django project
- Setup settings, PostgreSQL, Redis
- Buat `CustomUser`
- Setup auth dasar
- Role dan permission
- Data dusun dan perangkat desa

## Sprint 2

- Modul Publikasi Informasi
- CMS berita dan pengumuman

## Sprint 3

- Modul Layanan Administrasi
- Generator PDF
- Tracking status surat

## Sprint 4

- Modul Pengaduan Warga
- Riwayat tindak lanjut
- Upload bukti

## Sprint 5

- Modul Potensi Ekonomi
- Katalog BUMDes dan wisata

## Sprint 6

- Modul `homepage_konten`
- Endpoint agregat `GET /api/v1/homepage`
- Integrasi ringan ke `dashboard_admin`
  - content health
  - recent activity
  - quick action
  - completeness score

## Hardening

- Audit log
- Sentry
- Rate limiting
- Storage S3/MinIO
- Test dan hardening

## Phase 2

- Notifikasi WhatsApp/email
- QR verification surat
- Multi-template surat
- Dashboard performa perangkat
- Dashboard analitik phase 2 lebih dalam

## Relasi

- Mulai dari [[01 - Backend Architecture]]
- Data model dari [[08 - Database Schema]]
- Interface dari [[09 - API Endpoint Plan]]
- Hak akses dari [[11 - Access Matrix]]
- Flow dari [[13 - User Flows]]
- Homepage data dari [[14 - Homepage Data Mapping]]
- Dynamic homepage dari [[15 - Homepage Dynamic Backend Feature Plan]]
- Modul homepage dari [[16 - Modul Homepage Konten]]
