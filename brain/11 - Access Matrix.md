# Access Matrix

Tags: #access #permission #rbac

Ringkasan hak akses dari PRD revisi.

## Role

- `SUPERADMIN`
- `ADMIN`
- `BUMDES`
- `WARGA`

## Matrix inti

- Super Admin: akses semua modul, audit log penuh, kelola admin
- Admin Desa: kelola wilayah, publikasi, surat, pengaduan, akun warga
- Admin BUMDes: kelola unit usaha dan wisata
- Warga: lihat publik, ajukan surat, lihat surat sendiri, buat pengaduan, lihat pengaduan sendiri

## Rule endpoint

- Admin endpoint wajib auth + role check
- Data warga ikut prinsip least privilege
- Surat dan pengaduan harus punya pembatasan owner-scope untuk warga

## Relasi

- [[02 - Modul Auth Warga]]
- [[06 - Modul Layanan Administrasi]]
- [[07 - Modul Pengaduan Warga]]
- [[09 - API Endpoint Plan]]
