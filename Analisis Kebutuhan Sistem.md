## A. Kebutuhan Fungsional

1. Sistem dapat mengelola data dokter, mencakup nama dokter, jenis kelamin, spesialisasi, dan status kehadiran (Hadir, Izin, Sakit, Tugas Luar).
2. Sistem dapat mengelola data Kepala Poli berdasarkan bidang spesialisasi masing-masing.
3. Sistem dapat mengelola data alokasi ruangan dan kamar praktik yang tersedia.
4. Sistem dapat mengelola data unit Farmasi yang berkaitan dengan pelayanan kesehatan.
5. Sistem dapat menampilkan jadwal praktik dokter secara mingguan.
6. Sistem dapat menampilkan informasi terintegrasi berupa nama dokter, jenis kelamin, spesialisasi, Kepala Poli, hari dan jam praktik, ruangan/kamar praktik, serta unit Farmasi terkait.
7. Sistem dapat mencegah terjadinya bentrok jadwal penggunaan ruangan ketika terdapat jadwal dokter pada waktu dan ruangan yang sama (anti-conflict).

## B. Kebutuhan Nonfungsional
1. Kemudahan Penggunaan (Usability) : Sistem dirancang agar pengguna dapat melihat dan mengelola jadwal dokter dengan mudah dan intuitif.
2. Keterbacaan Tampilan (Interface) : Tampilan antarmuka bersifat sederhana dan terstruktur sehingga informasi jadwal dapat dibaca dengan jelas.
3. Akurasi Data (Accuracy) : Informasi jadwal yang ditampilkan akurat dan sesuai dengan data master yang telah diinputkan.
4. Keamanan Data (Security) : Sistem menerapkan pembatasan akses sehingga data tidak dapat diubah oleh pihak yang tidak memiliki hak akses.

## C. Aktor dan Proses Utama
1. Admin / Staf Pendukung : Menginput, mengubah, dan menghapus data dokter, Kepala Poli, ruangan, dan unit Farmasi, serta menyusun jadwal dan memeriksa validasi bentrok ruangan.
2. Kepala Poli : Melihat dan memantau kepastian rutinitas jadwal praktik dokter spesialis di bawah unit tanggung jawabnya.
3. Pasien : Melihat penayangan informasi jadwal praktik dokter mingguan, mencakup nama dokter, jenis kelamin, spesialisasi, hari, jam, dan kamar praktik.
4. Unit Farmasi : Melihat informasi jadwal praktik dokter mingguan yang terintegrasi dengan pelayanan farmasi.

## D. Hak Akses Aktor
Admin  
- Dapat menambah, membaca, mengubah, dan menghapus data dokter, Kepala Poli, ruangan, kamar, dan unit Farmasi.
- Dapat menyusun jadwal praktik dan memeriksa validasi bentrok.

Kepala Poli 
- Dapat melihat data dokter, Kepala Poli, ruangan, kamar, dan unit Farmasi.
- Dapat melihat jadwal praktik dokter di bawah unit tanggung jawabnya.

Pasien  
- Hanya dapat melihat jadwal praktik dokter mingguan.

Unit Farmasi  
- Hanya dapat melihat jadwal praktik dokter mingguan yang terintegrasi dengan pelayanan farmasi.
