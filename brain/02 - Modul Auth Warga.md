---
aliases:
- Auth Warga
architecture_node: '[[auth_warga]]'
status: linked_to_code
tags:
- feature
- auth
- user
title: Modul Auth Warga
---

# Modul Auth Warga

Bagian auth untuk [[01 - Backend Architecture]]. Ini modul paling matang di kode saat ini.

## Tujuan

- Login berbasis NIK
- Kelola akun warga dan admin
- Kontrol akses berdasar role
- Aktivasi dan nonaktif akun
- Sediakan endpoint `me`

## Aktor

- Warga
- Super Admin
- Admin Desa
- Admin BUMDes

## Entity utama

- `CustomUser`

Lihat: [[08 - Database Schema]]

## Struktur aktual modul

- `domain.py` = normalisasi dan validasi NIK, validasi role, exception domain
- `models.py` = `CustomUser` + `CustomUserManager`
- `repositories.py` = query user
- `permissions.py` = policy aktivasi, deaktivasi, create admin, create warga
- `services.py` = login, create account, activate, deactivate
- `views.py` = endpoint JSON berbasis function-based view
- `tests/` = domain, permission, service, view tests

## Aturan bisnis aktual

- `nik` wajib 16 digit dan dinormalisasi ke angka saja
- `role` valid hanya `SUPERADMIN`, `ADMIN`, `BUMDES`, `WARGA`
- akun nonaktif tidak boleh login
- `SUPERADMIN` saja boleh membuat akun admin
- `ADMIN`, `SUPERADMIN`, `BUMDES` boleh membuat akun warga
- user tidak boleh menonaktifkan akun sendiri
- admin biasa tidak boleh mengelola akun admin lain

## Endpoint aktual

- `POST /api/auth/login/`
- `POST /api/auth/logout/`
- `GET /api/auth/me/`
- `POST /api/auth/users/warga/create/`
- `POST /api/auth/users/admin/create/`
- `POST /api/auth/users/{user_id}/activate/`
- `POST /api/auth/users/{user_id}/deactivate/`

Lihat: [[09 - API Endpoint Plan]]

## Dependensi

- `toolbox.security.auth`
- `toolbox.security.permissions`
- `toolbox.logging.audit`
- Django auth backend
- Django Axes

## Risiko

- brute force login
- data NIK sensitif
- role escalation
- drift constant role kalau didefinisikan ganda

## Catatan arsitektur

> [!note]
> Modul ini pakai service layer dengan disiplin cukup baik. View tipis, rule inti di domain/service, query di repository.

> [!warning]
> Implementasi sekarang belum punya `change-password` dan belum expose list user admin seperti plan awal.

## Hak akses

- Super Admin kelola akun admin
- Internal admin (`SUPERADMIN`, `ADMIN`, `BUMDES`) kelola akun warga
- Warga hanya akses data sendiri lewat `me`

Lihat: [[11 - Access Matrix]]