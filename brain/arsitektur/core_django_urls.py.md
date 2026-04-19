---
title: core_django urls.py
tags:
  - backend
  - django
  - routing
type: architecture_leaf
aliases:
  - urls.py
---

# urls.py

Modul: [[core_django]]
Layer: Django URL Entry Point

## Peran

- expose `/admin/`
- include seluruh API Ninja di prefix `/api/v1/`

## Catatan

Source of truth:

- `path("api/v1/", include(api.urls[0]))`

Artinya:

- route name dari Django Ninja bisa di-`reverse()`
- semua feature API lewat registry [[core_django_api_v1.py]]
