---
title: publikasi_informasi
tags:
  - backend
  - django
  - feature
  - publikasi
  - cms
type: architecture_node
aliases:
  - Publikasi Informasi
  - CMS Berita
---

# publikasi_informasi

> [!abstract]
> Feature CMS desa untuk berita dan pengumuman. Menggunakan satu model `Publikasi` dengan field `jenis` dan status `DRAFT/PUBLISHED`.

## Komponen utama

- [[publikasi_informasi_models.py|models.py]]
- [[publikasi_informasi_domain.py|domain.py]]
- [[publikasi_informasi_permissions.py|permissions.py]]
- [[publikasi_informasi_repositories.py|repositories.py]]
- [[publikasi_informasi_services.py|services.py]]
- [[publikasi_informasi_api.py|api.py]]
- [[publikasi_informasi_admin.py|admin.py]]
- [[publikasi_informasi_apps.py|apps.py]]

## Rule penting

- draft tidak terlihat publik
- konten HTML disanitasi
- publish hanya admin desa/superadmin

## Legacy node

- [[publikasi_informasi_urls.py|urls.py (legacy)]]
- [[publikasi_informasi_views.py|views.py (legacy)]]
