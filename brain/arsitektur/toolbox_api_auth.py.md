---
title: toolbox api auth.py
tags:
  - backend
  - django
  - toolbox
  - auth
type: architecture_leaf
aliases:
  - toolbox/api/auth.py
---

# toolbox/api/auth.py

Layer: Shared API Auth

## Auth callable utama

- `AuthActiveUser`
- `AuthAdminOnly`
- `AuthBumdesManager`

## Peran

- menjadi auth bridge untuk Django Ninja
- dipakai lintas feature
- menjaga agar `api.py` feature tidak mengulang logic auth session dasar
