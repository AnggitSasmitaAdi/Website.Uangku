# UANGKU — Catatan Keuangan Pribadi

Aplikasi pencatatan pemasukan dan pengeluaran pribadi. Seluruh antarmuka (HTML, CSS, dan JavaScript) berada di satu berkas `web.html`. Flask menyediakan API transaksi, sedangkan data disimpan di SQLite pada `instance/uangku.sqlite3`.

## Jalankan lokal

```powershell
py -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
py app.py
```

Buka `http://127.0.0.1:5000`. Catatan akan tetap tersedia saat aplikasi dijalankan kembali di perangkat yang sama.

## Deploy ke Vercel

Vercel menggunakan filesystem serverless yang tidak persisten, sehingga SQLite lokal hanya cocok untuk pengembangan atau hosting pada server dengan disk persisten. Untuk memakai UANGKU di Vercel, hubungkan database persisten (misalnya Turso/libSQL atau PostgreSQL), lalu sesuaikan adapter penyimpanan. `DATABASE_PATH` dapat digunakan untuk menentukan lokasi SQLite pada hosting biasa.

## Berkas utama

- `web.html`: seluruh tampilan, stylesheet, dan interaksi browser.
- `app.py`: API transaksi, validasi, dan penyimpanan SQLite.
