# 🏢 Absensi Admin - Berjaya Group (PWA)

Aplikasi absensi berbasis **Progressive Web App (PWA)** untuk Divisi Admin Berjaya Group.

---

## 📁 Struktur File

```
/
├── index.html          ← Halaman utama absensi (SUDAH include PWA)
├── manifest.json       ← Konfigurasi PWA (nama, icon, warna)
├── sw.js               ← Service Worker (offline & caching)
├── favicon.ico         ← Favicon browser
└── icons/
    ├── icon-16x16.png
    ├── icon-32x32.png
    ├── icon-72x72.png
    ├── icon-96x96.png
    ├── icon-128x128.png
    ├── icon-144x144.png
    ├── icon-152x152.png
    ├── icon-180x180.png    ← Apple Touch Icon
    ├── icon-192x192.png    ← Wajib untuk Android
    ├── icon-384x384.png
    └── icon-512x512.png    ← Wajib untuk Splash Screen
```

---

## 🚀 Cara Upload ke GitHub Pages

### Langkah 1: Upload semua file
1. Buka repository GitHub Anda
2. Upload **semua file** di atas ke **root** repository (bukan dalam subfolder)
3. Pastikan struktur folder `icons/` juga ikut ter-upload

### Langkah 2: Aktifkan GitHub Pages
1. Buka **Settings** → **Pages**
2. Source: pilih **Deploy from a branch**
3. Branch: pilih **main** (atau master), folder **/ (root)**
4. Klik **Save**
5. Tunggu beberapa menit, lalu cek link yang diberikan GitHub

### Langkah 3: Test PWA
1. Buka link GitHub Pages di **Chrome/Samsung Browser** di HP
2. Akan muncul **banner install** di bawah layar
3. Klik "Install Sekarang" → app terpasang di Home Screen!

---

## 📱 Cara Install di HP

### Android (Chrome / Samsung Browser)
- Buka link → muncul banner **"Install Absensi Admin"** otomatis
- Klik **⬇️ Install Sekarang**

### iPhone / iPad (Safari)
- Buka link di **Safari**
- Muncul panduan: ketuk **Share** → **"Tambahkan ke Layar Utama"**
- Ketuk **Tambahkan**

---

## ✅ Fitur PWA

| Fitur | Status |
|-------|--------|
| Install di Home Screen | ✅ |
| Ikon khusus (logo Berjaya) | ✅ |
| Nama app: "Absensi Admin" | ✅ |
| Splash screen | ✅ |
| Offline caching | ✅ |
| Banner install otomatis | ✅ |
| Panduan iOS | ✅ |
| Theme color ungu | ✅ |

---

## 🔧 Konfigurasi

Edit `manifest.json` untuk mengubah:
- `name` → nama lengkap aplikasi
- `short_name` → nama singkat di icon
- `theme_color` → warna status bar
- `background_color` → warna splash screen

---

*Dibuat untuk Berjaya Group - Divisi Administrasi*
