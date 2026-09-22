# Mockup Aplikasi Pengelolaan Jadwal Dokter

## 1. Halaman Pilih Peran

Halaman ini adalah tampilan pertama saat aplikasi dibuka.
Bagian atas menampilkan judul aplikasi:
- APLIKASI JADWAL DOKTER
- RSUD ZAINAL ABIDIN PAGAR ALAM WAY KANAN

Di bawah judul terdapat teks:
"Silakan pilih peran:"

Lalu tersedia pilihan menu:
1. Admin / Staf Pendukung
2. Kepala Poli
3. Pasien
4. Unit Farmasi
0. Keluar

Fungsi:
- Menentukan hak akses pengguna.
- Admin dapat melakukan CRUD.
- Kepala Poli, Pasien, dan Unit Farmasi hanya dapat melihat jadwal.

## 2. Dashboard Admin
Halaman ini muncul setelah Admin masuk.
Bagian atas menampilkan judul "Dashboard Admin".
Di bawahnya terdapat ringkasan informasi:
- Total Dokter: 6
- Jadwal Minggu Ini: 18
- Kamar Terisi: 3
- Kamar Tersedia: 3

Setelah ringkasan, ditampilkan menu navigasi:
1. Data Dokter
2. Data Kepala Poli
3. Data Unit Farmasi
4. Data Poliklinik & Kamar
5. Kelola Jadwal Praktik
6. Cek Bentrok Jadwal
7. Lihat Jadwal Mingguan
0. Keluar

Fungsi:
- Menampilkan ringkasan data.
- Menjadi pusat navigasi ke seluruh modul.

## 3. Halaman Data Dokter
Halaman ini menampilkan form input data dokter.
Field yang tersedia:
- ID Personil
- Nama Dokter
- Jenis Kelamin (Laki-laki / Perempuan)
- Spesialisasi (Jantung, Gigi, Mata, Kulit, Paru-Paru, Bedah)
- Status Kehadiran (Hadir, Izin, Sakit, Tugas Luar)

Tombol yang tersedia:
- Simpan
- Ubah
- Hapus
- Batal

Di bawah form terdapat daftar dokter yang berisi kolom:
- ID
- Nama
- Jenis Kelamin
- Spesialisasi
- Status

Fungsi:
- Menambah, melihat, mengubah, dan menghapus data dokter.
- Mengatur status kehadiran dokter.
- Data ini menjadi sumber untuk pembuatan jadwal.

## 4. Halaman Data Kepala Poli
Halaman ini menampilkan form input data Kepala Poli.
Field yang tersedia:
- ID Kepala Poli
- Nama Kepala Poli
- Bidang Spesialis

Tombol yang tersedia:
- Simpan
- Ubah
- Hapus
- Batal

Di bawah form terdapat daftar Kepala Poli yang berisi kolom:
- ID
- Nama
- Bidang Spesialis

Fungsi:
- Mengelola data Kepala Poli untuk setiap bidang spesialisasi.
- Data ini digunakan sebagai bagian dari jadwal praktik.


## 5. Halaman Data Unit Farmasi
Halaman ini menampilkan form input data unit Farmasi.
Field yang tersedia:
- ID Farmasi
- Nama Unit Farmasi

Tombol yang tersedia:
- Simpan
- Ubah
- Hapus
- Batal

Di bawah form terdapat daftar unit Farmasi yang berisi kolom:
- ID
- Nama Unit Farmasi

Fungsi:
- Mengelola data unit Farmasi yang terhubung dengan pelayanan dokter.


## 6. Halaman Manajemen Poliklinik & Kamar
Halaman ini menampilkan daftar ruangan dan kamar praktik.
Bagian pertama menampilkan:
Poliklinik Gedung A
- Kamar 1: Terisi
- Kamar 2: Kosong
- Kamar 3: Terisi

Bagian kedua menampilkan:
Poliklinik Gedung B
- Kamar 4: Kosong
- Kamar 5: Terisi
- Kamar 6: Kosong

Tombol yang tersedia:
- Tambah Kamar
- Ubah Status
- Refresh

Fungsi:
- Mengelola 2 gedung dan 6 kamar praktik.
- Status kamar otomatis mengikuti status kehadiran dokter.


## 7. Halaman Form Jadwal Praktik
Halaman ini digunakan Admin untuk membuat jadwal praktik dokter.
Field yang tersedia:
- ID Jadwal
- Dokter (pilihan dari data dokter)
- Hari (Senin sampai Minggu)
- Jam Praktik
- Gedung (Poliklinik Gedung A / Gedung B)
- Kamar (Kamar 1 sampai Kamar 6)
- Kepala Poli (pilihan dari data Kepala Poli)
- Unit Farmasi (pilihan dari data unit Farmasi)

Tombol yang tersedia:
- Cek Bentrok
- Simpan
- Batal

Di bawah tombol terdapat status validasi, misalnya:
"Status Validasi: Tidak bentrok"
Fungsi:
- Menginput jadwal praktik dokter mingguan.
- Memeriksa bentrok sebelum jadwal disimpan.


## 8. Halaman Cek Bentrok Jadwal

Halaman ini digunakan untuk memeriksa apakah suatu kamar sudah dipakai pada waktu yang sama.
Field yang tersedia:
- Kamar
- Hari
- Jam

Tombol yang tersedia:
- Cek

Setelah tombol ditekan, hasil akan ditampilkan.

Contoh hasil jika bentrok:

"BENTROK!  
Kamar 1 sudah dipakai oleh:  
dr. Sari - Gigi - Senin 08:00-10:00"

Contoh hasil jika tidak bentrok:

"Tidak ada bentrok. Jadwal dapat disimpan."

Fungsi:
- Mencegah dua dokter memakai kamar dan waktu yang sama.
- Menggunakan method cekBentrok.

## 9. Halaman Jadwal Praktik Dokter Mingguan
Halaman ini adalah output utama aplikasi.
Bagian atas menampilkan judul "Jadwal Praktik Dokter Mingguan".
Di bawahnya terdapat filter:
- Spesialis
- Hari
- Gedung

Setelah filter, ditampilkan tabel jadwal dengan kolom:
- No
- Nama Dokter
- Jenis Kelamin
- Spesialisasi
- Kepala Poli
- Hari
- Jam
- Ruangan / Kamar
- Unit Farmasi

Contoh isi tabel:
1. dr. Andi - L - Jantung - dr. Budi - Senin - 08:00-10:00 - Gd A / Kamar 1 - Farmasi A  
2. dr. Sari - P - Gigi - dr. Rina - Senin - 10:00-12:00 - Gd A / Kamar 2 - Farmasi B  
3. dr. Maya - P - Mata - dr. Dedi - Selasa - 08:00-10:00 - Gd B / Kamar 4 - Farmasi A

Tombol yang tersedia:
- Cetak
- Refresh
- Kembali

Fungsi:
- Menampilkan jadwal praktik dokter mingguan secara lengkap.
- Menjadi sumber informasi utama bagi semua aktor.
- Dapat difilter sesuai kebutuhan pengguna.

## 10. Halaman Jadwal untuk Pasien, Kepala Poli, dan Unit Farmasi
Halaman ini memiliki tampilan yang sama dengan halaman jadwal mingguan, tetapi hanya bersifat melihat.
Bagian atas menampilkan judul "Jadwal Dokter Mingguan".
Filter yang tersedia:
- Cari Dokter
- Spesialis
- Hari

Di bawah filter ditampilkan tabel jadwal mingguan.

Tombol yang tersedia:
- Cetak
- Kembali

Fungsi:
- Menampilkan jadwal sesuai hak akses.
- Tidak ada tombol tambah, ubah, atau hapus.
- Kepala Poli melihat jadwal bidangnya.
- Pasien melihat seluruh jadwal dokter.
- Unit Farmasi melihat jadwal yang terintegrasi dengan farmasi.

## 11. Konfirmasi Hapus Data
Halaman ini muncul saat pengguna menekan tombol Hapus.
Isi halaman:
"Apakah Anda yakin ingin menghapus data ini?"

Di bawahnya ditampilkan informasi data yang akan dihapus:
- ID
- Nama

Tombol yang tersedia:
- Ya, Hapus
- Batal

Fungsi:
- Mencegah penghapusan data secara tidak sengaja.
