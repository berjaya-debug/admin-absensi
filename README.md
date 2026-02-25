# 📋 Absensi Divisi Admin

## Arsitektur

```
GitHub Pages          Apps Script (satu URL deploy)
─────────────         ──────────────────────────────
index.html            ?page=Admin       → Admin.html
  │                   ?page=UangMakan   → UangMakan.html
  │ fetch POST        
  └──────────────────► doPost → prosesAbsenAdmin()
  │ fetch GET         
  └──────────────────► doGet  → getStaffList (JSON)
```

## File

| File | Lokasi | Metode komunikasi |
|------|--------|-------------------|
| `index.html` | GitHub Pages | `fetch` POST/GET ke GAS URL |
| `Admin.html` | Apps Script project | `google.script.run` |
| `UangMakan.html` | Apps Script project | `google.script.run` |
| `Code.gs` | Apps Script project | — |

---

## Setup

### 1. Apps Script

1. Buka [script.google.com](https://script.google.com) → buat project baru
2. Isi `Code.gs` → ganti `SS_ID_ADMIN` dengan ID spreadsheet Anda
3. Tambah file HTML baru: **Admin** dan **UangMakan** → paste isi masing-masing
4. Deploy → **New Deployment** → Web App → Execute as: **Me** → Access: **Anyone**
5. Copy URL deploy (contoh: `https://script.google.com/macros/s/XXX/exec`)

### 2. index.html (GitHub Pages)

1. Buka `index.html`, ganti baris:
   ```js
   const GAS_URL = "https://script.google.com/macros/s/XXXXX/exec";
   ```
2. Upload ke repository GitHub → aktifkan GitHub Pages

---

## URL Akses

| Halaman | URL |
|---------|-----|
| Absensi Staff | `https://username.github.io/repo/` |
| Data Absensi | `https://script.google.com/macros/s/XXX/exec?page=Admin` |
| Rekap NBM | `https://script.google.com/macros/s/XXX/exec?page=UangMakan` |

---

## Struktur Spreadsheet

### Sheet: `Staff`
| A (Nama) |
|----------|
| Nama Staff 1 |

### Sheet: `Sheet1`
| A | B | C | D | E | F | G | H | I | J |
|---|---|---|---|---|---|---|---|---|---|
| Timestamp | Nama | Lat | Lon | Jarak | Status | Foto | Tipe | Lokasi | **Urgent** |

> Kolom **J**: isi `TRUE` manual untuk lembur Minggu/merah yang urgent (Rp 150.000)

---

## Aturan NBM

| Hari | Batas normal | Lembur |
|------|-------------|--------|
| Senin–Jumat | 17.00 | +2 jam → Rp 30.000 · +4 jam → Rp 60.000 |
| Sabtu | 15.00 | +2 jam → Rp 30.000 · +4 jam → Rp 60.000 |
| Minggu | — | Urgent: Rp 150.000 · Non-urgent: Rp 60.000 |

**NBM harian: Rp 27.500**
