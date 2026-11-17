# Dashboard Monitoring Digitalisasi Sekolah Vokasi 2026 (SUMKAL - 10 UID)

Web dashboard statis untuk memantau progres dukungan kelistrikan **Program Digitalisasi Pembelajaran Sekolah Vokasi Tahun 2026** wilayah Sumatera & Kalimantan (10 UID/UIW) yang terhubung langsung ke tab `SUMKAL` di Google Sheets.

## Struktur File
- `index.html` — Antarmuka dashboard interaktif (KPI Cards, Grafik per UID & Jenjang, Tabel Rekap, Peta Sebaran Sekolah, dan Tabel Rincian).
- `app.js` — Mesin penarik data langsung dari Google Sheets (`SUMKAL`) + filter & visualisasi.
- `data/sumkal_snapshot.csv` — Data cadangan (*fallback*) agar dashboard tetap langsung tampil saat dibuka pertama kali.
- `.github/workflows/sync_data.yml` — Otomatisasi GitHub Actions untuk mencadangkan snapshot CSV secara berkala.

## Cara Mengaktifkan di GitHub Pages (3 Langkah)
1. **Isi ID Google Sheets Anda di `app.js`:**
   - Buka file `app.js`, ganti `TEMPEL_ID_GOOGLE_SHEETS_ANDA_DI_SINI` dengan ID Google Sheets Anda.
   - Pastikan Google Sheets Anda disetel **Share $\rightarrow$ Anyone with the link (Viewer)** agar browser bisa menarik CSV tab `SUMKAL` secara langsung.
2. **Upload ke Repository GitHub:**
   - Buat repository baru di GitHub (misalnya `Vokasi-SUMKAL-2026`), lalu unggah seluruh isi folder ini (`index.html`, `app.js`, folder `data/`, dan folder `.github/`).
3. **Aktifkan GitHub Pages:**
   - Masuk ke **Settings $\rightarrow$ Pages** di repository GitHub Anda.
   - Pada bagian **Build and deployment $\rightarrow$ Source**, pilih **Deploy from a branch** $\rightarrow$ pilih branch **`main`** dan folder **`/ (root)`** $\rightarrow$ klik **Save**.
   - Tunggu 1–2 menit hingga tautan `https://<username>.github.io/Vokasi-SUMKAL-2026/` aktif.
