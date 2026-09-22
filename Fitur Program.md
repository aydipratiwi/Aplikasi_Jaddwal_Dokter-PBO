# Fitur Aplikasi Pengelolaan Jadwal Dokter

## 1. Daftar Fitur

| Kode | Fitur | Aktor | Deskripsi | Class Terkait |
|---|---|---|---|---|
| F-01 | Pilih Peran / Login | Semua | Menentukan hak akses pengguna: Admin, Kepala Poli, Pasien, Unit Farmasi | — |
| F-02 | Dashboard Admin | Admin | Menampilkan ringkasan jumlah dokter, jadwal, kamar terisi, dan kamar tersedia | Semua |
| F-03 | CRUD Data Dokter | Admin | Tambah, lihat, ubah, hapus data dokter; atur status kehadiran | `PersonilMedis`, `DokterSpesialis` |
| F-04 | CRUD Data Kepala Poli | Admin | Kelola data Kepala Poli berdasarkan bidang spesialisasi | `KepalaPoli` |
| F-05 | CRUD Data Unit Farmasi | Admin | Kelola data unit Farmasi yang terkait pelayanan | `UnitFarmasi` |
| F-06 | CRUD Poliklinik & Kamar | Admin | Kelola Poliklinik Gedung A/B dan Kamar 1–6 | `Poliklinik`, `KamarPraktik` |
| F-07 | Buat Jadwal Praktik | Admin | Input jadwal praktik dokter mingguan | `JadwalPraktik` |
| F-08 | Validasi Bentrok Jadwal | Admin | Cek bentrok kamar dan waktu sebelum jadwal disimpan | `JadwalPraktik.cekBentrok()` |
| F-09 | Update Status Kamar Otomatis | Sistem | Status kamar mengikuti status kehadiran dokter | `JadwalPraktik.updateOtomatisStatusKamar()` |
| F-10 | Jadwal Praktik Dokter Mingguan | Admin, Kepala Poli, Pasien, Farmasi | Menampilkan jadwal mingguan lengkap | `JadwalPraktik.cetakJadwalMingguan()` |
| F-11 | Filter Jadwal | Semua | Filter berdasarkan hari, spesialisasi, gedung, atau dokter | `JadwalPraktik` |
| F-12 | Hak Akses Pengguna | Sistem | Admin dapat CRUD; Kepala Poli, Pasien, Farmasi hanya melihat | — |
| F-13 | Cetak / Export Jadwal | Admin | Cetak atau simpan jadwal mingguan | `JadwalPraktik` |


## 2. Detail Fitur

### F-01 Pilih Peran / Login
- Pengguna memilih peran:
  - Admin / Staf Pendukung
  - Kepala Poli
  - Pasien
  - Unit Farmasi
- Hak akses menyesuaikan peran.

### F-02 Dashboard Admin
- Menampilkan:
  - Total dokter
  - Jumlah jadwal minggu ini
  - Kamar terisi
  - Kamar tersedia
- Navigasi ke seluruh modul.

### F-03 CRUD Data Dokter
- Field:
  - `idPersonil`
  - `nama`
  - `jenisKelamin`
  - `spesialisasi`
  - `statusKehadiran`
- Spesialisasi: Jantung, Gigi, Mata, Kulit, Paru-Paru, Bedah.
- Status: Hadir, Izin, Sakit, Tugas Luar.
- Operasi: Create, Read, Update, Delete.

### F-04 CRUD Data Kepala Poli
- Field:
  - `idKepalaPoli`
  - `namaKepalaPoli`
  - `bidangSpesialis`
- Digunakan untuk integrasi jadwal.

### F-05 CRUD Data Unit Farmasi
- Field:
  - `idFarmasi`
  - `namaUnitFarmasi`
- Digunakan untuk integrasi jadwal.

### F-06 CRUD Poliklinik & Kamar
- Data:
  - Poliklinik Gedung A: Kamar 1, 2, 3
  - Poliklinik Gedung B: Kamar 4, 5, 6
- Status kamar:
  - Terisi / Dipakai
  - Kosong / Tersedia

### F-07 Buat Jadwal Praktik
- Field:
  - `idJadwal`
  - `hari`
  - `jamPraktik`
  - `dokter`
  - `kamar`
  - `kepalaPoli`
  - `farmasi`
- Jadwal disimpan jika tidak bentrok.

### F-08 Validasi Bentrok Jadwal
- Method: `cekBentrok(jadwalLain)`
- Aturan:
  - Tidak boleh ada dua dokter berbeda pada kamar dan waktu yang sama.
- Jika bentrok: jadwal ditolak.

### F-09 Update Status Kamar Otomatis
- Jika dokter `Hadir` → kamar `Terisi / Dipakai Praktik`.
- Jika dokter `Izin`, `Sakit`, atau `Tugas Luar` → kamar `Kosong / Tersedia`.

### F-10 Jadwal Praktik Dokter Mingguan
- Output utama:
  - Nama Dokter
  - Jenis Kelamin
  - Spesialisasi
  - Kepala Poli Spesialis
  - Hari & Jam Praktik
  - Ruangan Poli & Kamar Praktik
  - Unit Farmasi Terkait

### F-11 Filter Jadwal
- Filter:
  - Hari
  - Spesialisasi
  - Gedung
  - Dokter

### F-12 Hak Akses Pengguna
- Admin: CRUD semua data.
- Kepala Poli: melihat jadwal bidangnya.
- Pasien: melihat jadwal mingguan.
- Unit Farmasi: melihat jadwal terkait farmasi.

### F-13 Cetak / Export Jadwal
- Cetak jadwal mingguan.
- Export sederhana (txt / csv / pdf jika dikembangkan).



## 3. Alur Proses Utama

- Admin input dokter
  - data masuk ke DokterSpesialis
  - status kehadiran disimpan
   
- Admin buat jadwal
  - pilih dokter, hari, jam, kamar
  -  sistem panggil cekBentrok()
  -  jika bentrok = tolak
  -  jika tidak bentrok = simpan
  -  updateOtomatisStatusKamar()
       - Hadir : Terisi
       - Izin/Sakit/Tugas Luar : Kosong

- Pasien / Kepala Poli / Farmasi
  - buka Jadwal Mingguan
  - filter
  - lihat informasi lengkap
