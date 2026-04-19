---
title: profil_wilayah
tags:
  - backend
  - django
  - feature
  - profil
  - wilayah
type: architecture_node
aliases:
  - Profil Wilayah
---

# profil_wilayah

> [!abstract]
> Feature untuk data dusun, perangkat desa, dan profil desa. Menyediakan endpoint publik untuk profil desa dan endpoint admin untuk CRUD.

## Komponen utama

- [[profil_wilayah_models.py|models.py]]
- [[profil_wilayah_domain.py|domain.py]]
- [[profil_wilayah_permissions.py|permissions.py]]
- [[profil_wilayah_repositories.py|repositories.py]]
- [[profil_wilayah_services.py|services.py]]
- [[profil_wilayah_api.py|api.py]]
- [[profil_wilayah_admin.py|admin.py]]
- [[profil_wilayah_apps.py|apps.py]]

## Rule penting

- hanya admin dan superadmin bisa mengubah data
- perangkat publik hanya yang `is_published=True`
- foto perangkat melewati validator upload

## Legacy node

- [[profil_wilayah_urls.py|urls.py (legacy)]]
- [[profil_wilayah_views.py|views.py (legacy)]]
