---
title: dashboard_admin permissions.py
tags:
  - backend
  - django
  - permission
  - dashboard
type: architecture_leaf
aliases:
  - dashboard_admin/permissions.py
---

# permissions.py

Modul: [[dashboard_admin]]
Layer: Permission helper

## Rule

- hanya user aktif
- harus `is_staff`
- dipakai untuk akses dashboard admin
