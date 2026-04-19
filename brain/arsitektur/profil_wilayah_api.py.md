---
title: profil_wilayah api.py
tags:
  - backend
  - django
  - api
  - profil
type: architecture_leaf
aliases:
  - profil_wilayah/api.py
---

# api.py

Modul: [[profil_wilayah]]
Layer: Presentation / API

## Endpoint utama

- profil publik agregat
- CRUD dusun admin
- CRUD perangkat admin
- update profil desa

## Catatan

- publik route belum memakai envelope `{ data: ... }`
- create perangkat menerima multipart untuk foto
