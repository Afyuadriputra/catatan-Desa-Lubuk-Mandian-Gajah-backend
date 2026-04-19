---
title: layanan_administrasi api.py
tags:
  - backend
  - django
  - api
  - surat
type: architecture_leaf
aliases:
  - layanan_administrasi/api.py
---

# api.py

Modul: [[layanan_administrasi]]
Layer: Presentation / API

## Endpoint penting

- ajukan surat
- list surat
- detail surat
- proses surat
- download PDF

## Kontrak

Ada dua keluarga endpoint:

- endpoint existing
- endpoint `mvp/*` dengan envelope `{ data: ... }`

## Catatan

> [!note]
> Route name penting:
> - `surat-ajukan`
> - `surat-list`
> - `surat-detail`
> - `surat-proses`
> - `surat-download-pdf`
