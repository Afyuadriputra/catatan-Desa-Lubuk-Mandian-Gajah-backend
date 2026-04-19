---
title: Homepage Frontend Dynamic Review
tags:
  - frontend
  - homepage
  - review
  - dynamic-content
aliases:
  - Review Homepage Dynamic Frontend
---

# Homepage Frontend Dynamic Review

## Ringkasan

Homepage frontend sudah pakai satu source data dari `GET /api/v1/homepage` via `homepageApi.getPublic()`.

Split UI tetap terpisah:
- desktop
- mobile

## Temuan Review

### Sudah aman dynamic

- Komponen desktop dan mobile sudah baca prop `data`, bukan impor `homepage.data.ts` langsung.
- Wrapper page fetch data sekali, lalu pass ke layout desktop/mobile yang sama-sama consume prop.
- Source utama render sekarang backend, bukan static file.
- Field editorial utama sudah terbaca dari API:
  - `brand.*`
  - `tagline`
  - `heroImage`
  - `heroDescription`
  - `naming*`
  - `culture*`
  - `sialang*`
  - `peat*`
  - `recoveryItems`
  - `potentials`
  - `facilities`
  - `gallery`
  - `contact.*`
  - `footer*`

### Sudah diperbaiki saat review

- `HeroSection` desktop sekarang render `heroBadge`.
- `HeroMobile` sekarang pakai `heroDescription`, bukan copy static lokal.
- `QuickStatsMobile` sekarang pakai `quickStatsDescription`.
- `QuickStatsMobile` sekarang fallback ke 4 stat pertama bila label prioritas tidak ada.
- `PeatSection` desktop aman bila `peatImages` tidak lengkap.
- `PeatMobile` aman bila `peatImages` kosong.
- `GalleryMobile` aman bila `gallery` kosong.
- `ContactSection` dan `ContactMobile` sekarang pakai link Google Maps dari `contact.address`, bukan koordinat/static placeholder.
- `ContactSection` desktop sekarang pakai link WhatsApp dari `contact.whatsapp`.
- Copy editorial section intro sekarang punya owner backend baru:
  - `recoveryTitle`
  - `recoveryDescription`
  - `potentialTitle`
  - `potentialOpportunitiesTitle`
  - `galleryTitle`
  - `galleryDescription`
  - `contactTitle`
  - `contactDescription`

## Residual Gap

> [!note]
> `homepage.data.ts` masih ada sebagai fallback seed lokal. Saat ini dipakai hanya jika SSR gagal menjangkau backend, bukan sebagai source utama.

- Beberapa heading/copy presentasional masih hardcoded di komponen.
- Ini tidak memblokir dynamic content, karena field utama tetap datang dari backend.
- Yang sengaja tetap hardcoded:
  - label UI kecil seperti `Info`, `Galeri`, `Kontak Desa`
  - hint interaksi seperti `Geser untuk melihat`
  - copy dekoratif/non-domain yang lebih cocok hidup di layer presentasi
- Env penting frontend:
  - `API_BASE_URL`
  - `NEXT_PUBLIC_API_BASE_URL`
- Mapper `HomepageDataDto -> HomepageData` sekarang jadi layer normalisasi utama.
- Guard image kosong sudah ditambahkan untuk navbar, hero, naming, sialang, dan contact map.

## Next Step

- Jika backend deployment sudah stabil, hapus fallback `homepage.data.ts`.
- Tambah validasi visual melalui build/lint frontend saat environment Node siap.
- Bangun admin UI untuk edit field scalar homepage yang sekarang sudah tersedia di backend.

Lihat juga: [[14 - Homepage Data Mapping]] dan [[16 - Modul Homepage Konten]]
