---
title: pengaduan_warga api.py
tags:
  - backend
  - django
  - api
  - pengaduan
type: architecture_leaf
aliases:
  - pengaduan_warga/api.py
---

# api.py

Modul: [[pengaduan_warga]]
Layer: Presentation / API

## Endpoint penting

- buat pengaduan
- list pengaduan
- detail pengaduan
- proses pengaduan

## Catatan

- create pengaduan menerima multipart untuk foto bukti
- endpoint `mvp/*` dipakai untuk contract frontend yang konsisten
- route name penting:
  - `pengaduan-buat`
  - `pengaduan-list`
  - `pengaduan-detail`
  - `pengaduan-proses`
