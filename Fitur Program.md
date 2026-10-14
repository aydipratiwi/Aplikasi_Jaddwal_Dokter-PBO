# Fitur Aplikasi Pengelolaan Jadwal Dokter

## 1. Daftar Fitur

| Kode | Fitur | Aktor | Deskripsi | Class Terkait |
|---|---|---|---|---|
| F-01 | Pilih Peran / Login | Semua aktor | Menentukan peran pengguna dan hak aksesnya. | Belum ditentukan |
| F-02 | Dashboard Admin | Admin | Menampilkan ringkasan informasi pengelolaan dokter, jadwal, dan kamar praktik. | Menyesuaikan implementasi |
| F-03 | Pengelolaan Data Dokter | Admin | Mengelola identitas, spesialisasi, dan status kehadiran dokter. | `PersonilMedis`, `DokterSpesialis` |
| F-04 | Pengelolaan Unit Farmasi | Admin | Mengelola data unit Farmasi yang berkaitan dengan pelayanan. | `UnitFarmasi` |
| F-05 | Pengelolaan Poliklinik dan Kamar | Admin | Mengelola data poliklinik dan enam kamar praktik. | `Poliklinik`, `KamarPraktik` |
| F-06 | Pembuatan Jadwal Praktik | Admin, Manajemen | Menyusun jadwal berdasarkan dokter, hari, jam, kamar, dan unit Farmasi. | `JadwalPraktik` |
| F-07 | Validasi Bentrok Jadwal | Admin, Manajemen | Memeriksa bentrok penggunaan kamar sebelum jadwal disimpan. | `JadwalPraktik` |
| F-08 | Pembaruan Status Kamar | Sistem | Menyesuaikan status kamar berdasarkan status kehadiran dokter sesuai aturan sistem. | `DokterSpesialis`, `KamarPraktik`, `JadwalPraktik` |
| F-09 | Tampilan Jadwal Praktik Mingguan | Semua aktor | Menampilkan informasi jadwal dokter secara terstruktur. | `JadwalPraktik` |
| F-10 | Filter Jadwal | Admin, Manajemen, Dokter, Unit Farmasi, Pasien | Menyaring jadwal berdasarkan hari, spesialisasi, gedung, atau dokter. | `JadwalPraktik` |
| F-11 | Cetak / Ekspor Jadwal | Admin | Menyediakan keluaran jadwal mingguan untuk dokumentasi. | `JadwalPraktik` |

Catatan: fitur login, dashboard, filter, dan ekspor perlu disesuaikan dengan implementasi program yang dikembangkan.

## 2. Detail Fitur

### F-01 Pilih Peran / Login

Pengguna memilih peran atau melakukan login untuk mengakses sistem sesuai dengan hak aksesnya. Aktor dalam sistem meliputi Admin, Manajemen, Dokter, Unit Farmasi, dan Pasien.

### F-02 Dashboard Admin

Dashboard dirancang untuk menampilkan ringkasan informasi pengelolaan data dokter, jadwal praktik, dan kondisi kamar. Informasi yang ditampilkan disesuaikan dengan data yang tersedia dalam sistem.

### F-03 Pengelolaan Data Dokter

Admin mengelola data dokter yang meliputi ID personil, nama, jenis kelamin, spesialisasi, dan status kehadiran.

Spesialisasi yang digunakan meliputi Jantung, Gigi, Mata, Kulit, Paru-paru, dan Bedah. Status kehadiran meliputi Hadir, Izin, Sakit, dan Tugas Luar.

### F-04 Pengelolaan Unit Farmasi

Admin mengelola ID Farmasi dan nama unit Farmasi yang berkaitan dengan jadwal praktik dokter.

### F-05 Pengelolaan Poliklinik dan Kamar

Sistem mengelola dua lokasi poliklinik, yaitu Poliklinik Gedung A dengan Kamar 1–3 dan Poliklinik Gedung B dengan Kamar 4–6. Setiap kamar memiliki nomor dan status penggunaan.

### F-06 Pembuatan Jadwal Praktik

Admin atau Manajemen menentukan dokter, hari, jam praktik, kamar, dan unit Farmasi terkait. Jadwal diperiksa sebelum disimpan.

### F-07 Validasi Bentrok Jadwal

Sistem memeriksa kemungkinan penggunaan kamar pada hari dan interval waktu yang sama. Jika terjadi bentrok, jadwal harus diperbaiki sebelum disimpan.

### F-08 Pembaruan Status Kamar

Sistem menyesuaikan status kamar berdasarkan status kehadiran dokter sesuai dengan aturan yang ditetapkan dalam implementasi aplikasi.

### F-09 Tampilan Jadwal Praktik Mingguan

Sistem menampilkan nama dokter, jenis kelamin, spesialisasi, hari dan jam praktik, lokasi poliklinik, nomor kamar, serta unit Farmasi terkait.

### F-10 Filter Jadwal

Pengguna dapat menyaring jadwal berdasarkan hari, spesialisasi, gedung, atau dokter agar informasi lebih mudah ditemukan.

### F-11 Cetak / Ekspor Jadwal

Admin dapat menggunakan fitur ini untuk memperoleh salinan jadwal mingguan sebagai dokumentasi apabila fitur tersebut telah diimplementasikan.

## 4. Alur Proses Utama

1. Admin mengelola data dokter, unit Farmasi, poliklinik, dan kamar praktik.
2. Admin atau Manajemen menyusun jadwal praktik dokter.
3. Sistem melakukan validasi bentrok jadwal.
4. Jika terjadi bentrok, jadwal diperbaiki.
5. Jika tidak terjadi bentrok, jadwal disimpan.
6. Sistem memperbarui status kamar sesuai aturan yang berlaku.
7. Pengguna melihat jadwal praktik mingguan dan dapat menggunakan filter.
8. Admin dapat mencetak atau mengekspor jadwal apabila fitur tersedia.
