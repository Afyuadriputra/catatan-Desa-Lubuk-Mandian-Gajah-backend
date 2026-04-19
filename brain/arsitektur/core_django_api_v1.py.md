---
title: core_django api_v1.py
tags:
  - backend
  - django
  - ninja
  - routing
type: architecture_leaf
aliases:
  - api_v1.py
---

# api_v1.py

Modul: [[core_django]]
Layer: Interface / API Registry

## Peran

- membuat instance `NinjaAPI`
- memasang global exception handler
- mendaftarkan router dari semua feature

## Router aktif

- `/auth`
- `/dashboard-admin`
- `/layanan-administrasi`
- `/pengaduan`
- `/potensi-ekonomi`
- `/profil-wilayah`
- `/publikasi`

## Dampak arsitektur

> [!info]
> Semua endpoint backend sekarang terkumpul di satu registry. Karena itu, route naming dan contract API lintas feature lebih mudah distabilkan untuk frontend dan testing.
