<div align="center">

# 🌱 Magplant Resource Pack

**Resource pack resmi untuk plugin Magplant di PaperMC 1.20.1**
*Model & tekstur 3D kustom untuk mesin Magplant dan Magplant Remote, ala Magplant 5000 di Growtopia.*

![Minecraft Version](https://img.shields.io/badge/Minecraft-1.20.1-4CAF50?style=for-the-badge&logo=minecraft&logoColor=white)

</div>

---

## 📖 Tentang

Repo ini adalah **hosting tidak resmi sekaligus arsip** untuk resource pack Magplant. Pack ini memuat model 3D dan tekstur kustom (`CustomModelData`) agar item **Magplant** dan **Magplant Remote** tampil sesuai di dalam game.

Tanpa pack ini plugin tetap jalan, tapi Magplant tampil sebagai Lodestone vanilla dan Remote sebagai Ender Eye biasa, dan item yang melayang di tengah Magplant tertutup badan bloknya.

### ✨ Fitur

- **Model 3D transparan:** Magplant berupa rangka biru, bagian tengahnya terbuka, jadi item yang melayang di tengahnya terlihat, seperti di Growtopia.
- **Remote 3D:** Perangkat kecil biru dengan layar cyan, tombol merah, dan antena kuning.
- **Tier berbeda warna:** Bentuk rangka sama, warna dan hiasan beda.
  - **Basic** — biru, `CustomModelData 1`
  - **Advanced** — hijau + hiasan emas, `CustomModelData 3`
  - **Ultimate** — ungu + hiasan emas, `CustomModelData 4`
- **Ringan:** Ukuran zip sekitar 12 KB, cepat diunduh player saat join.
- **Kompatibel 1.20.1:** `pack_format: 15`, tanpa peringatan *outdated pack*.

## 📦 Download

Download zip terbaru dari halaman **Releases** di repo ini:

**[Magplant-ResourcePack.zip v1.3.0](https://github.com/aiqqqfdh/Magplant-Plugin/releases/download/v1.3.0/Magplant-ResourcePack.zip)**

SHA1 (v1.3.1):

```
8b30c7f829bfcef938fe3909a6b6e0d480543ecc
```

> Kalau kamu update pack, hitung SHA1 baru dengan `sha1sum Magplant-ResourcePack.zip` di Linux atau `certutil -hashfile Magplant-ResourcePack.zip SHA1` di Windows.

## 🖥️ Cara pasang di server (otomatis, direkomendasikan)

Server bisa mengirim pack ini otomatis saat player join. Matikan server dulu, lalu edit `server.properties`:

```properties
resource-pack=https://github.com/aiqqqfdh/Magplant-Plugin/releases/download/v1.3.0/Magplant-ResourcePack.zip
resource-pack-sha1=96a8572bd60020fc05fab20146317a15c1e7b3b1
resource-pack-prompt=Magplant Resource Pack - wajib untuk tekstur Magplant
require-resource-pack=true
```

Contoh lengkapnya ada di [`server.properties.example`](server.properties.example).

Simpan, nyalakan lagi server, lalu join. Akan muncul prompt resource pack, klik Yes / Accept.

`require-resource-pack=true` artinya player harus terima pack-nya. Set ke `false` kalau mau player boleh menolak, tapi tampilannya jadi vanilla.

## 👤 Cara pasang manual (player)

1. Download `Magplant-ResourcePack.zip` dari Releases.
2. Copy ke folder `resourcepacks` di Minecraft kamu.
3. Di game: Options > Resource Packs, pindahkan pack ke kanan dan aktifkan.

## 📁 Isi repo

```
.
├── README.md
├── server.properties.example
└── resourcepack/
    ├── pack.mcmeta
    └── assets/
        ├── magplant/
        │   ├── models/item/
        │   │   ├── magplant.json            # Basic, CMD 1
        │   │   ├── magplant_advanced.json   # Advanced, CMD 3
        │   │   ├── magplant_ultimate.json   # Ultimate, CMD 4
        │   │   └── magplant_remote.json     # Remote, CMD 2
        │   └── textures/
        └── minecraft/
            ├── models/block/lodestone.json  # Rangka transparan Magplant
            └── models/item/
                ├── lodestone.json           # Override CMD 1/3/4
                └── ender_eye.json           # Override CMD 2
```

> File PNG tekstur ada di dalam zip Release, karena GitHub tidak menampilkan preview-nya dengan baik di repo ini. Source JSON dan `pack.mcmeta` ada lengkap di folder `resourcepack/`.

Untuk membuat ulang zip dari folder ini:

```bash
cd resourcepack
zip -r ../Magplant-ResourcePack.zip .
```

## 🔌 Plugin Magplant

Pack ini hanya berisi tekstur dan model. Plugin-nya (jar) dipasang terpisah di folder `plugins/` server Paper 1.20.1:

- `/magplant give <player> [tier]` — tier `basic`, `advanced`, atau `ultimate`
- `/magplant list` — lihat Magplant aktif
- `/magplant reload` — reload config

Fitur plugin V1.3.0: teks melayang di atas Magplant, lampu status, peringatan saat penuh, isi tersimpan saat Magplant dihancurkan, efek collect yang bisa diaktifkan/nonaktifkan, dan tier Advanced/Ultimate.

## 📝 Changelog

### v1.3.0
- Tier Advanced (hijau + emas, CMD 3) dan Ultimate (ungu + emas, CMD 4)
- Model rangka sama, warna dan hiasan beda per tier

### v1.2.0
- Model 3D rangka transparan, item melayang di tengah terlihat
- Remote 3D

### v1.1.0
- Tekstur custom pertama, Magplant biru dan Remote biru
