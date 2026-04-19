---
title: potensi_ekonomi api.py
tags:
  - backend
  - django
  - api
  - ekonomi
type: architecture_leaf
aliases:
  - potensi_ekonomi/api.py
---

# api.py

Modul: [[potensi_ekonomi]]
Layer: Presentation / API

## Endpoint publik

- katalog publik anonim
- detail unit anonim

## Endpoint admin

- list admin
- create unit
- update unit
- delete unit

## Catatan

- create endpoint bisa multipart karena upload foto
- route name penting:
  - `ekonomi-katalog`
  - `ekonomi-detail`
  - `ekonomi-admin-list`
  - `ekonomi-admin-buat`
  - `ekonomi-admin-update`
  - `ekonomi-admin-delete`
