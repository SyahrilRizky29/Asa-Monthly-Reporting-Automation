# Asa Monthly Reporting Automation 📊🚀

Sistem otomatisasi laporan performa bulanan yang mengonsolidasi data dari berbagai sumber (Multiple Google Sheets) menjadi satu ringkasan eksekutif yang akurat dan siap saji.

## 🌟 Fitur Utama
- **Konsolidasi Data Otomatis**: Menggabungkan transaksi dari 3 sumber berbeda menggunakan logika **Append** (Vertikal) untuk menjamin akurasi data.
- **Standarisasi Header**: Node JavaScript cerdas yang menyamakan format kolom berbeda secara otomatis.
- **Pembersihan Data Duplikat**: Menggunakan filter "ID Laporan" untuk mencegah penghitungan ganda.
- **Penjadwalan (Scheduling)**: Berjalan otomatis setiap tanggal 1 pukul 08.00 pagi.
- **Notifikasi Eksekutif**: Ringkasan dikirim langsung ke Telegram Bot dan Email Manajemen.

## 🛠️ Tech Stack
- **n8n**: Workflow Automation Platform.
- **JavaScript**: Pemrosesan logika data & agregasi.
- **Google Sheets API**: Sebagai database sumber data.
- **Telegram & SMTP**: Saluran notifikasi otomatis.

## 🚀 Panduan Instalasi (Tutorial)

Ikuti langkah-langkah di bawah ini untuk menjalankan workflow ini di instance n8n Anda:

### 1. Prasyarat
- Memiliki akun [n8n](https://n8n.io/) (Self-hosted atau Cloud).
- Memiliki kredensial **Google Cloud Console** (untuk Google Sheets & Gmail).
- Memiliki **Bot Telegram** (buat melalui @BotFather) dan `Chat ID` Anda.

### 2. Import Workflow
1. Download file `Asa_Laporan_Bulanan.json` dari repositori ini.
2. Buka n8n, klik **Workflows** > **Import from File**.
3. Pilih file yang sudah didownload.

### 3. Konfigurasi Kredensial
- Buka node **Google Sheets** (Data Sheet 1, 2, dan 3) dan hubungkan dengan akun Google Anda.
- Buka node **Telegram** dan masukkan `Bot Token` serta `Chat ID` Anda.
- Buka node **Gmail** dan atur koneksi SMTP/OAuth2 Anda.

### 4. Pengaturan Spreadsheet
- Pastikan ID Spreadsheet pada node Google Sheets sudah mengarah ke file dummy Anda.
- **Penting**: Gunakan mode **Append** pada node Merge agar data tertumpuk secara vertikal (jangan gunakan Combine by Position).

### 5. Jalankan!
Klik **Execute Workflow** untuk menguji coba. Jika berhasil, data akan terkumpul di Master Sheet dan notifikasi akan masuk ke Telegram/Email Anda.

## 📝 Catatan Tambahan
Jika output Anda kosong, pastikan kolom **"Bulan"** pada Spreadsheet sudah berisi data untuk bulan berjalan (contoh: "April") dan tahun yang sesuai (contoh: "2026").

## 👤 Author
**Muhammad Syahril Rizky Fauzan** *IT Student & Automation Enthusiast* NF Academy - Group 4 (2026)
