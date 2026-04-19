---
title: pengaduan_warga
tags:
  - backend
  - django
  - feature
  - pengaduan
type: architecture_node
aliases:
  - Pengaduan Warga
---

# pengaduan_warga

> [!abstract]
> Feature pengaduan warga. Menangani pembuatan pengaduan, upload bukti, tracking status, catatan admin, dan histori tindak lanjut.

## Komponen utama

- [[pengaduan_warga_models.py|models.py]]
- [[pengaduan_warga_domain.py|domain.py]]
- [[pengaduan_warga_permissions.py|permissions.py]]
- [[pengaduan_warga_repositories.py|repositories.py]]
- [[pengaduan_warga_services.py|services.py]]
- [[pengaduan_warga_api.py|api.py]]
- [[pengaduan_warga_admin.py|admin.py]]
- [[pengaduan_warga_apps.py|apps.py]]

## Status pengaduan

- `OPEN`
- `TRIAGED`
- `IN_PROGRESS`
- `RESOLVED`
- `CLOSED`

## Rule penting

- warga hanya melihat pengaduannya sendiri
- admin melihat semua
- notes wajib saat `RESOLVED/CLOSED`
- histori tindak lanjut wajib tersimpan

## Legacy node

- [[pengaduan_warga_urls.py|urls.py (legacy)]]
- [[pengaduan_warga_views.py|views.py (legacy)]]
