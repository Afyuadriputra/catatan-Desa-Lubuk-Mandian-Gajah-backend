---
title: publikasi_informasi api.py
tags:
  - backend
  - django
  - api
  - cms
type: architecture_leaf
aliases:
  - publikasi_informasi/api.py
---

# api.py

Modul: [[publikasi_informasi]]
Layer: Presentation / API

## Endpoint publik

- list published
- detail published

## Endpoint admin

- create publikasi
- update publikasi
- ubah status
- delete publikasi

## Catatan

- detail publik MVP menyembunyikan field `status`
- route name penting:
  - `publikasi-publik-list`
  - `publikasi-detail`
  - `publikasi-admin-buat`
  - `publikasi-admin-update`
  - `publikasi-admin-ubah-status`
  - `publikasi-admin-delete`
