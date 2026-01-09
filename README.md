# Sistem Manajemen Pendaftaran & Paspor

Aplikasi web dinamis dan interaktif untuk mengelola data pendaftaran mahasiswa, daftar ulang, dan pengurusan paspor.

##  Fitur Utama

### 1. **Input Data Pendaftar**
- Tambah data pendaftar baru dengan auto-generate nomor daftar
- Input: Nama, Tanggal Lahir, Jenis Kelamin, Alamat, No. Telepon, Email
- Tanggal dan jam pendaftaran otomatis
- Pencatatan kapasitas pendaftaran (1 jam untuk 5 orang)
- Status: Pending, Approved, Closed
- CRUD Operations (Create, Read, Update, Delete)

### 2. **Daftar Ulang** 
- Proses ulang pendaftaran dengan validasi data
- Input: No. KTP, No. Ijazah, Tanggal dan Jam Ulang
- Verifikasi status keterangan (OK / Tidak OK)
- Manajemen status approval
- Pencatatan data ulang untuk setiap pendaftar

### 3. **Pengurusan Paspor**
- Manajemen pengurusan paspor dengan nomor paspor unik
- Pencatatan tanggal terbit, berlaku, dan expired
- Perhitungan biaya otomatis (Rp 355.000)
- Status: Pending, Processing, Selesai, Closed
- Tracking proses pengurusan

### 4. **Laporan Ringkasan**
- Statistik total pendaftar (Approved vs Pending)
- Statistik daftar ulang yang disetujui
- Total biaya paspor yang dikumpulkan
- Dashboard dengan visualisasi data

##  Database Schema

**3 Tabel Utama:**

1. **pendaftar**
   - id, no_daftar (auto-generate), nama_pendaftar, tgl_lahir
   - jenis_kelamin, alamat, no_telepon, email
   - tgl_daftar, jam_daftar, status, keterangan

2. **daftar_ulang**
   - id, no_daftar (FK), nama_pendaftar, tgl_lahir
   - ktp, no_ijazah, tgl_ulang, jam_ulang
   - status, keterangan

3. **pengurusan_paspor**
   - id, no_daftar (FK), nama_pendaftar, no_paspor
   - tgl_terbit, tgl_berlaku, tgl_expired
   - status, keterangan, biaya

##  Cara Menggunakan

### Setup
1. Letakkan folder `tugas uas` di `C:\xampp\htdocs\`
2. Buka browser: `http://localhost/tugas%20uas`
3. Database akan dibuat otomatis saat akses pertama

### Operasi Dasar
- **Tambah Data**: Isi form dan klik "Simpan"
- **Approve**: Klik tombol "Approve" pada tabel
- **Hapus**: Klik tombol "Hapus" pada tabel
- **Lihat Laporan**: Klik tab "Laporan"

##  Struktur File

```
tugas uas/
├── index.php                 (Halaman utama)
├── includes/
│   ├── database.php         (Koneksi & setup DB)
│   └── functions.php        (Fungsi-fungsi CRUD)
├── actions/
│   ├── add_pendaftar.php    (Tambah pendaftar)
│   ├── add_daftar_ulang.php (Tambah daftar ulang)
│   ├── add_paspor.php       (Tambah paspor)
│   ├── delete.php           (Hapus data)
│   ├── approve.php          (Approve data)
│   └── get_data.php         (Ambil data untuk tabel)
└── assets/
    ├── css/
    │   └── style.css        (Styling responsif)
    └── js/
        └── script.js        (Fungsi-fungsi JS)
```

## Teknologi Yang Digunakan

- **Frontend**: HTML5, CSS3, JavaScript (Vanilla)
- **Backend**: PHP 7.4+
- **Database**: MySQL
- **Server**: XAMPP (Apache + PHP + MySQL)

## Fitur Teknis

- ✅ Responsive Design (Mobile, Tablet, Desktop)
- ✅ AJAX untuk operasi tanpa refresh
- ✅ Input validation
- ✅ Error handling
- ✅ Auto-generate nomor daftar
- ✅ Foreign Key relationships
- ✅ Status tracking
- ✅ Laporan statistik real-time

## 📝 Note

- Biaya paspor default: Rp 355.000 (bisa diubah saat input)
- Nomor daftar format: YYYYMMDDXXXX (Contoh: 202501001)
- Semua field dengan * adalah wajib diisi
- Data disimpan dengan timestamp otomatis

---

**Dibuat untuk memenuhi Tugas UAS - Sistem Informasi Manajemen Data Pendaftaran & Paspor**
