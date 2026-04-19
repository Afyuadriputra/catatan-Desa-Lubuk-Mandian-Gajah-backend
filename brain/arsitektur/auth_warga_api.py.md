---
title: auth_warga api.py
tags:
  - backend
  - django
  - api
  - auth
type: architecture_leaf
aliases:
  - auth_warga/api.py
---

# api.py

Modul: [[auth_warga]]
Layer: Presentation / API

## Tanggung jawab

- deklarasi endpoint auth
- bind `AuthActiveUser` dan `AuthAdminOnly`
- memanggil `AuthService`
- mengaktifkan session login dengan `login(request, user)`

## Ciri implementasi sekarang

- memakai Django Ninja router
- route name penting sudah stabil untuk frontend/testing
- shape response campuran:
  - schema langsung untuk endpoint utama auth
  - contract stabil via route name untuk integrasi
