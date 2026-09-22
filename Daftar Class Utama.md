Daftar Class Utama Aplikasi Pengelolaan Jadwal Dokter
Berikut adalah daftar class utama beserta atribut, method, dan penerapannya dalam perancangan aplikasi:
## 1. PersonilMedis (Abstract Class)
- Atributnya
  - 'idPersonil' : String
  - 'nama' : String
  - 'jenisKelamin' : String
- Methodnya:
  - `getIdPersonil()` : String
  - `getNama()` : String
  - `getJenisKelamin()` : String
  - `tampilkanProfil()` : void (Abstract Method)

## 2. DokterSpesialis (Child Class dari PersonilMedis)
- Atributnya:
  - `spesialisasi` : String (Jantung, Gigi, Mata, Kulit, Paru, Bedah)
  - `statusKehadiran` : String (Hadir, Izin, Sakit, Tugas Luar)
- Methodnya:
  - `setStatusKehadiran(status : String)` : void
  - `getStatusKehadiran()` : String
  - `getSpesialisasi()` : String
  - `tampilkanProfil()` : void (Overriding)

## 3. KepalaPoli
- Atributnya:
  - `idKepalaPoli` : String
  - `namaKepalaPoli` : String
  - `bidangSpesialis` : String
- Methodnya:
  - `getNamaKepalaPoli()` : String
  - `getBidangSpesialis()` : String

## 4. UnitFarmasi
- Atributnya:
  - `idFarmasi` : String
  - `namaUnitFarmasi` : String
- Methodnya:
  - `getNamaUnitFarmasi()` : String

## 5. KamarPraktik
- Atributnya:
  - `nomorKamar` : int (Kamar 1–6)
  - `statusKamar` : String (Terisi / Dipakai, Kosong / Tersedia)
- Methodnya:
  - `setStatusKamar(status : String)` : void
  - `getStatusKamar()` : String
  - `getNomorKamar()` : int

## 6. Poliklinik
- Atributnya:
  - `namaGedung` : String (Poliklinik Gedung A, Poliklinik Gedung B)
  - `daftarKamar` : List<KamarPraktik>
- Methodnya:
  - `tambahKamar(kamar : KamarPraktik)` : void
  - `getDaftarKamar()` : List<KamarPraktik>

## 7. JadwalPraktik
-Atributnya:
  - `idJadwal` : String
  - `hari` : String
  - `jamPraktik` : String
  - `dokter` : DokterSpesialis
  - `kamar` : KamarPraktik
  - `kepalaPoli` : KepalaPoli
  - `farmasi` : UnitFarmasi
- Methodnya
  - `cekBentrok(jadwalLain : JadwalPraktik)` : boolean
  - `updateOtomatisStatusKamar()` : void
  - `cetakJadwalMingguan()` : void
