---
title: potensi_ekonomi
tags:
  - backend
  - django
  - feature
  - ekonomi
  - bumdes
type: architecture_node
aliases:
  - Potensi Ekonomi
  - BUMDes
---

# potensi_ekonomi

> [!abstract]
> Feature untuk katalog unit usaha desa dan wisata. Menyediakan endpoint publik anonim dan endpoint admin untuk pengelolaan data ekonomi desa.

## Komponen utama

- [[potensi_ekonomi_models.py|models.py]]
- [[potensi_ekonomi_domain.py|domain.py]]
- [[potensi_ekonomi_permissions.py|permissions.py]]
- [[potensi_ekonomi_repositories.py|repositories.py]]
- [[potensi_ekonomi_services.py|services.py]]
- [[potensi_ekonomi_api.py|api.py]]
- [[potensi_ekonomi_admin.py|admin.py]]
- [[potensi_ekonomi_apps.py|apps.py]]

## Kategori

- `KOPERASI`
- `WISATA`
- `JASA`

## Rule penting

- data publik hanya yang `is_published`
- role kelola:
  - `BUMDES`
  - `ADMIN`
  - `SUPERADMIN`
- deskripsi/fasilitas disanitasi

## Legacy node

- [[potensi_ekonomi_urls.py|urls.py (legacy)]]
- [[potensi_ekonomi_views.py|views.py (legacy)]]
