---
title: auth_warga
tags:
  - backend
  - django
  - feature
  - auth
type: architecture_node
aliases:
  - Auth Warga
---

# auth_warga

> [!abstract]
> Feature autentikasi dan manajemen akun. Mengelola login session Django, create akun warga/admin, aktivasi akun, nonaktif akun, dan ganti password.

## Komponen utama

- [[auth_warga_models.py|models.py]]
- [[auth_warga_domain.py|domain.py]]
- [[auth_warga_permissions.py|permissions.py]]
- [[auth_warga_repositories.py|repositories.py]]
- [[auth_warga_services.py|services.py]]
- [[auth_warga_api.py|api.py]]
- [[auth_warga_admin.py|admin.py]]
- [[auth_warga_apps.py|apps.py]]

## Peran arsitektural

- `models.py`: custom user model berbasis `nik`
- `domain.py`: validasi NIK, role, perubahan password
- `permissions.py`: policy manage user
- `repositories.py`: akses ORM user
- `services.py`: login, create akun, activation lifecycle
- `api.py`: endpoint HTTP via Django Ninja

## Endpoint utama

- `POST /api/v1/auth/login`
- `POST /api/v1/auth/logout`
- `GET /api/v1/auth/me`
- `POST /api/v1/auth/users/warga/create`
- `POST /api/v1/auth/users/admin/create`
- `POST /api/v1/auth/users/{user_id}/activate`
- `POST /api/v1/auth/users/{user_id}/deactivate`
- `POST /api/v1/auth/change-password`

## Dependensi penting

- [[core_django]]
- [[toolbox_api_auth.py|toolbox/api/auth.py]]
- `django.contrib.auth`
- `django-axes`

## Legacy node

- [[auth_warga_urls.py|urls.py (legacy)]]
- [[auth_warga_views.py|views.py (legacy)]]
