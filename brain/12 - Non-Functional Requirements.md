# Non-Functional Requirements

Tags: #nfr #security #performance

Kebutuhan non-fungsional dari PRD revisi.

## Performa

- P95 endpoint baca < 300 ms
- P95 endpoint tulis < 700 ms
- Generate PDF normal < 10 detik

## Ketersediaan

- Uptime bulanan >= 99.5%
- Maintenance di luar jam kerja bila bisa

## Keamanan

- Password hash bawaan Django
- Rate limiting aktif
- Sanitasi HTML aktif
- Audit log aktif untuk data penting
- Least privilege
- Validasi tipe dan ukuran upload

## Logging dan monitoring

- Error ke Sentry
- Event penting ke audit log
- App log untuk troubleshooting

## Backup

- Backup DB harian
- Backup media terjadwal

## Relasi

- [[01 - Backend Architecture]]
- [[04 - Modul Publikasi Informasi]]
- [[06 - Modul Layanan Administrasi]]
- [[07 - Modul Pengaduan Warga]]
