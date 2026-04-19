---
title: Homepage Data Mapping
tags:
  - frontend
  - backend
  - architecture
  - homepage
  - mapping
aliases:
  - Mapping Homepage Data
---

# Homepage Data Mapping

> [!abstract]
> Mapping field `HomepageData` dari frontend static ke arsitektur backend Django saat ini. Tujuan note ini: menentukan owner feature backend untuk tiap field dan menghindari salah taruh data homepage ke feature yang tidak tepat.

## Kesimpulan cepat

> [!success]
> Data homepage **bisa** digabung ke backend.

> [!warning]
> Tapi **jangan** paksa semua field masuk `[[profil_wilayah]]`.

Rekomendasi owner:

- `[[profil_wilayah]]` untuk identitas desa inti, profil, wilayah, kontak dasar
- `[[potensi_ekonomi]]` untuk potensi usaha / wisata yang benar-benar data ekonomi
- `[[publikasi_informasi]]` untuk berita / pengumuman yang akan tampil di homepage
- feature baru `homepage_konten` untuk konten landing page yang sifatnya editorial / branding / storytelling

## Kategori mapping

### 1. Cocok ke feature existing sekarang

| Field frontend | Owner backend | Catatan |
| --- | --- | --- |
| `villageName` | `[[profil_wilayah]]` | Identitas desa utama |
| `heroDescription` | `[[profil_wilayah]]` | Bisa diturunkan dari profil desa / deskripsi desa |
| `stats[Dusun]` | `[[profil_wilayah]]` | Bisa dihitung dari data dusun |
| `contact.address` | `[[profil_wilayah]]` | Alamat kantor/desa sebaiknya milik profil desa |
| `potentials` | `[[potensi_ekonomi]]` | Bisa diambil dari unit usaha / wisata published |
| `potentialQuote` | `[[potensi_ekonomi]]` atau `homepage_konten` | Jika narasi umum, lebih cocok `homepage_konten` |
| data berita/pengumuman homepage | `[[publikasi_informasi]]` | Ambil list published terbaru |

### 2. Bisa diturunkan dari backend, bukan disimpan persis

| Field frontend | Sumber | Catatan |
| --- | --- | --- |
| `stats` | agregasi banyak feature | Sebagian bukan field DB langsung |
| `quickStatsDescription` | `homepage_konten` atau agregasi profil | Narasi, bukan angka |
| `stats[unit usaha/wisata]` | `[[potensi_ekonomi]]` | Hasil hitung |
| `stats[publikasi]` jika nanti ada | `[[publikasi_informasi]]` | Hasil hitung |

### 3. Tidak punya rumah yang pas di feature existing

> [!note]
> Ini mayoritas data homepage static kamu sekarang. Sifatnya ==landing content==, bukan data wilayah inti, bukan berita, bukan ekonomi murni.

| Field frontend | Owner yang disarankan | Alasan |
| --- | --- | --- |
| `tagline` | `homepage_konten` | Branding landing page |
| `heroImage` | `homepage_konten` | Media hero editorial |
| `heroBadge` | `homepage_konten` | Label visual homepage |
| `brand.logoUrl` | `homepage_konten` | Branding visual |
| `brand.logoAlt` | `homepage_konten` | Metadata branding |
| `brand.regionLabel` | `homepage_konten` | Label visual/branding |
| `contact.whatsapp` | `homepage_konten` atau `[[profil_wilayah]]` | Jika WA resmi desa, bisa ke profil; jika CTA website, bisa ke homepage_konten |
| `contact.mapImage` | `homepage_konten` | Bukan data inti domain |
| `namingTitle` | `homepage_konten` | Storytelling landing page |
| `namingDescription` | `homepage_konten` | Storytelling landing page |
| `namingImage` | `homepage_konten` | Media editorial |
| `namingQuote` | `homepage_konten` | Copywriting |
| `cultureTitle` | `homepage_konten` | Section landing page |
| `cultureDescription` | `homepage_konten` | Section landing page |
| `cultureCards` | `homepage_konten` | Editorial blocks |
| `sialangTitle` | `homepage_konten` | Section landing page |
| `sialangDescription` | `homepage_konten` | Section landing page |
| `sialangImage` | `homepage_konten` | Media section |
| `sialangBadge` | `homepage_konten` | UI label |
| `sialangStat` | `homepage_konten` | Bisa angka editorial/manual |
| `sialangQuote` | `homepage_konten` | Copywriting |
| `peatTitle` | `homepage_konten` | Section landing page |
| `peatDescription` | `homepage_konten` | Section landing page |
| `peatQuote` | `homepage_konten` | Copywriting |
| `peatImages` | `homepage_konten` | Gallery section |
| `recoveryItems` | `homepage_konten` | Storytelling blocks |
| `potentialOpportunityItems` | `homepage_konten` | Opportunity cards, bukan data unit usaha mentah |
| `facilitiesTitle` | `homepage_konten` | Section title |
| `facilities` | `homepage_konten` atau feature baru fasilitas | Sekarang belum ada feature fasilitas |
| `gallery` | `homepage_konten` | Gallery landing page |
| `footerLinks` | `homepage_konten` | Konfigurasi navigasi website |
| `footerDescription` | `homepage_konten` | Copywriting |
| `officeHours` | `homepage_konten` atau `[[profil_wilayah]]` | Jika jam layanan resmi, bisa masuk profil desa |
| `footerBadges` | `homepage_konten` | Branding visual |
| `footerCopyright` | `homepage_konten` | Konfigurasi website |

## Mapping final per feature

### `[[profil_wilayah]]`

Masuk akal untuk:

- nama desa
- alamat desa / kantor
- profil desa inti
- visi, misi, sejarah
- dusun
- perangkat
- sebagian statistik wilayah
- kemungkinan jam layanan resmi

### `[[potensi_ekonomi]]`

Masuk akal untuk:

- potensi usaha / wisata nyata
- unit published untuk homepage
- data detail kontak usaha
- fasilitas usaha/wisata jika memang milik unit usaha

### `[[publikasi_informasi]]`

Masuk akal untuk:

- berita terbaru di homepage
- pengumuman terbaru di homepage

### `homepage_konten` (feature baru disarankan)

Masuk akal untuk:

- hero section
- branding section
- budaya
- naming story
- sialang section
- peat / gambut section
- recovery section
- gallery homepage
- facilities homepage
- footer config
- static CTA / badge / quote

## Kenapa tidak semua ke `[[profil_wilayah]]`

> [!danger]
> Kalau semua homepage static dimasukkan ke `profil_wilayah`, feature itu jadi rusak secara semantik.

Masalah:

- domain wilayah jadi campur branding website
- galeri dan hero marketing tercampur dengan data dusun/perangkat
- sulit maintain
- sulit dites
- frontend sulit bedakan data domain vs data landing page

## Rekomendasi arsitektur API

### Opsi terbaik

Buat feature baru:

- `homepage_konten`

Lalu expose 1 endpoint agregat:

- `GET /api/v1/homepage`

Response:

- `profil` dari `[[profil_wilayah]]`
- `potensi` dari `[[potensi_ekonomi]]`
- `publikasi_terbaru` dari `[[publikasi_informasi]]`
- `landing_content` dari `homepage_konten`

### Opsi minimal

Tanpa feature baru dulu:

- homepage frontend panggil 3 endpoint:
  - profil publik
  - publikasi publik
  - potensi ekonomi publik
- sisa konten tetap static di frontend

Ini cocok kalau migrasi bertahap.

## Strategi migrasi bertahap

### Tahap 1

- pindahkan data yang sudah punya owner jelas:
  - profil publik
  - potensi ekonomi
  - publikasi terbaru

### Tahap 2

- buat feature `homepage_konten`
- pindahkan hero, branding, budaya, sialang, gambut, gallery, footer

### Tahap 3

- buat endpoint agregat `homepage`
- frontend tidak lagi konsumsi static file penuh

## Keputusan praktis

> [!success]
> Jawaban paling tepat:
>
> - **bisa** masuk backend
> - **jangan** masuk ke satu feature lama saja
> - **owner final**:
>   - `[[profil_wilayah]]`
>   - `[[potensi_ekonomi]]`
>   - `[[publikasi_informasi]]`
>   - `homepage_konten` sebagai feature baru

## Referensi

- [[03 - Modul Profil Wilayah]]
- [[04 - Modul Publikasi Informasi]]
- [[05 - Modul Potensi Ekonomi]]
- [[01 - Backend Architecture]]
- [[profil_wilayah]]
- [[publikasi_informasi]]
- [[potensi_ekonomi]]
