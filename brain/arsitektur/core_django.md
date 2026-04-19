---
title: core_django
tags:
  - backend
  - django
  - architecture
  - core
type: architecture_node
aliases:
  - Core Django
---

# Core Django

> [!abstract]
> Node ini menjelaskan entry point backend Django saat ini. Source of truth routing API ada di `core_django`, lalu semua modul feature diregistrasikan ke Django Ninja.

## Peran

- memuat settings global Django
- menjadi entry point URL project
- meregistrasikan semua router API feature
- menjadi boundary antara runtime Django dan modul feature

## Komponen inti

- [[core_django_settings.py|settings.py]]
- [[core_django_urls.py|urls.py]]
- [[core_django_api_v1.py|api_v1.py]]
- [[core_django_asgi.py|asgi.py]]
- [[core_django_wsgi.py|wsgi.py]]

## Alur request

```mermaid
graph TD
    A[HTTP Request] --> B[core_django_urls.py]
    B --> C[include api.urls[0]]
    C --> D[core_django_api_v1.py]
    D --> E[Feature Router]
    E --> F[api.py per feature]
    F --> G[services.py]
    G --> H[domain.py / repositories.py / toolbox]
```

## Router yang diregistrasikan

- [[auth_warga]]
- [[dashboard_admin]]
- [[layanan_administrasi]]
- [[pengaduan_warga]]
- [[potensi_ekonomi]]
- [[profil_wilayah]]
- [[publikasi_informasi]]

## Catatan arsitektur

> [!note]
> Backend sekarang memakai **Django Ninja**, bukan pola lama `urls.py + views.py` per feature.

> [!warning]
> Beberapa node lama di vault masih bernama `*_urls.py.md` dan `*_views.py.md`. Node itu sekarang harus dibaca sebagai ==legacy reference==, bukan source of truth implementasi API saat ini.
