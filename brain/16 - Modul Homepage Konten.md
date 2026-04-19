---
title: Modul Homepage Konten
tags:
  - feature
  - homepage
  - backend
  - cms
aliases:
  - Homepage Konten
  - homepage_konten
architecture_node: '[[homepage_konten]]'
status: linked_to_code
---

# Modul Homepage Konten

Modul CMS ringan untuk konten editorial homepage publik.

> [!info]
> Modul ini bukan owner data domain desa inti. Modul ini owner untuk hero, branding, story section, gallery, footer, dan blok editorial homepage.

## Tujuan

- membuat homepage frontend tidak lagi full static
- memisahkan data domain desa dari konten landing page
- memberi admin API khusus untuk kelola homepage

## Owner data

- hero
- branding
- naming story
- culture section
- sialang section
- peat / gambut section
- recovery items
- opportunities
- facilities homepage
- gallery
- contact intro dan contact CTA copy
- footer links dan footer copy
- scalar editorial tambahan:
  - `recoveryTitle`
  - `recoveryDescription`
  - `potentialTitle`
  - `potentialOpportunitiesTitle`
  - `galleryTitle`
  - `galleryDescription`
  - `contactTitle`
  - `contactDescription`

## Entity utama

- `HomepageContent`
- `HomepageCultureCard`
- `HomepageRecoveryItem`
- `HomepagePotentialOpportunityItem`
- `HomepageFacility`
- `HomepageGalleryItem`
- `HomepageFooterLink`
- `HomepageStatisticItem`

## Endpoint aktual

- `GET /api/v1/homepage`
- `GET /api/v1/homepage/admin/content`
- `PUT /api/v1/homepage/admin/content`
- `POST /api/v1/homepage/admin/culture-cards`
- `PUT /api/v1/homepage/admin/culture-cards/{item_id}`
- `DELETE /api/v1/homepage/admin/culture-cards/{item_id}`
- pola sama untuk:
  - `recovery-items`
  - `potential-opportunities`
  - `facilities`
  - `gallery`
  - `footer-links`
- `POST /api/v1/homepage/admin/stats`
- `PUT /api/v1/homepage/admin/stats/{item_id}`
- `DELETE /api/v1/homepage/admin/stats/{item_id}`

## Dependensi

- `[[03 - Modul Profil Wilayah]]` untuk `dusun` dan profil dasar
- `[[05 - Modul Potensi Ekonomi]]` untuk `potentials`
- `[[dashboard_admin]]` untuk content health, recent activity, quick action

## Aturan bisnis

- publik boleh akses `GET /api/v1/homepage`
- hanya internal admin boleh kelola konten homepage
- singleton `HomepageContent` sebagai pusat field scalar
- child item pakai `sort_order` agar urutan frontend stabil
- statistik homepage manual disimpan sebagai child item agar admin bisa atur tanpa ubah schema lagi

## Status implementasi

> [!success]
> Sudah aktif di codebase.

- endpoint publik aktif
- endpoint admin aktif
- test API ada
- sudah terhubung ringan ke `[[dashboard_admin]]`
- frontend homepage publik sudah pakai `GET /api/v1/homepage` sebagai source utama
- frontend punya mapper DTO -> view model untuk normalisasi data
- fallback seed lokal masih ada untuk kasus backend tidak bisa dijangkau saat SSR

## Relasi

- [[14 - Homepage Data Mapping]]
- [[15 - Homepage Dynamic Backend Feature Plan]]
- [[01 - Backend Architecture]]
