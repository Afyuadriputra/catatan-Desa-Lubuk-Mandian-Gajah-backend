---
title: layanan_administrasi
tags:
  - backend
  - django
  - feature
  - surat
type: architecture_node
aliases:
  - Layanan Administrasi
  - Surat
---

# layanan_administrasi

> [!abstract]
> Feature layanan surat desa. Menangani pengajuan, tracking status, proses admin, histori status, dan PDF final.

## Komponen utama

- [[layanan_administrasi_models.py|models.py]]
- [[layanan_administrasi_domain.py|domain.py]]
- [[layanan_administrasi_permissions.py|permissions.py]]
- [[layanan_administrasi_repositories.py|repositories.py]]
- [[layanan_administrasi_services.py|services.py]]
- [[layanan_administrasi_api.py|api.py]]
- [[layanan_administrasi_admin.py|admin.py]]
- [[layanan_administrasi_apps.py|apps.py]]

## Domain penting

Jenis surat:

- `SKU`
- `SKTM`
- `DOMISILI`

Status:

- `PENDING`
- `VERIFIED`
- `PROCESSED`
- `DONE`
- `REJECTED`

## Rule penting

- warga hanya lihat surat miliknya sendiri
- admin/superadmin lihat semua
- state machine status dijaga di domain
- reject wajib alasan
- PDF hanya valid saat `DONE`
- histori perubahan status disimpan

## Dependensi penting

- [[toolbox_pdf_generator.py|toolbox/pdf_generator]]
- [[toolbox_api_auth.py|toolbox/api/auth.py]]
- [[core_django]]

## Legacy node

- [[layanan_administrasi_urls.py|urls.py (legacy)]]
- [[layanan_administrasi_views.py|views.py (legacy)]]
