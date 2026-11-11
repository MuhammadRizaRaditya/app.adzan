# 07 Identifikasi Class

Berikut adalah class-class yang diperlukan untuk membangun aplikasi SALATIFY beserta evaluasi kebutuhan:

---

## 1. User

### Tanggung Jawab
Class User mengelola akun pengguna, autentikasi, dan profil pengguna dalam sistem SALATIFY.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| user_id | int | + | ID unik pengguna |
| username | str | + | Nama pengguna |
| email | str | + | Email pengguna |
| password | str | - | Kata sandi (terhash) |
| full_name | str | # | Nama lengkap pengguna |
| phone_number | str | # | Nomor telepon |
| profile_picture | str | # | Path gambar profil |
| created_at | datetime | + | Tanggal registrasi |
| last_login | datetime | # | Waktu login terakhir |
| is_active | bool | + | Status akun aktif/matikan |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| register | username, email, password, full_name | bool | + | Mendaftar akun baru |
| login | email, password | User | + | Masuk ke sistem |
| logout | None | None | + | Keluar dari sistem |
| update_profile | full_name, phone_number, profile_picture | bool | # | Update profil pengguna |
| get_profile | None | dict | + | Mendapatkan data profil |
| validate_password | password | bool | # | Validasi password |

---

## 2. JadwalSholat

### Tanggung Jawab
Class JadwalSholat menghitung dan menyediakan jadwal sholat harian berdasarkan lokasi pengguna.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| schedule_id | int | + | ID jadwal |
| user_id | int | + | ID pengguna yang terkait |
| tanggal | date | + | Tanggal jadwal |
| subuh | time | + | Jam sholat Subuh |
| dzuhur | time | + | Jam sholat Dzuhur |
| ashar | time | + | Jam sholat Ashar |
| maghrib | time | + | Jam sholat Maghrib |
| isya | time | + | Jam sholat Isya |
| waktu_selisih | timedelta | + | Waktu hingga sholat berikutnya |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| hitung_jadwal | latitude, longitude, tanggal | JadwalSholat | + | Hitung jadwal berdasarkan lokasi |
| get_jadwal_terdekat | None | list | + | Dapatkan jadwal sholat terdekat |
| update_jadwal | schedule_id, data_baru | bool | + | Update jadwal sholat |
| get_waktu_remaining | None | timedelta | + | Dapatkan waktu hingga sholat |

---

## 3. PengingatSholat

### Tanggung Jawab
Class PengingatSholat mengelola pengaktifan/pemotongan pengingat dan waktu settingannya.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| reminder_id | int | + | ID pengingat |
| user_id | int | + | ID pengguna |
| waktu_pengingat | time | + | Jam pengingat |
| menit_sebelum | int | + | Menit sebelum shalat |
| status_aktif | bool | + | Aktif/nonaktif pengingat |
| tipe | str | + | Jenis pengingat (suara, vibrasi, dll) |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| set_pengingat | waktu, menit_sebelum, status | bool | + | Set pengingat shalat |
| toggle_pengingat | None | bool | + | Aktifkan/nonaktifkan pengingat |
| get_setting_pengingat | None | dict | + | Dapatkan setting pengingat |
| hapus_pengingat | reminder_id | bool | + | Hapus pengingat |

---

## 4. Lokasi

### Tanggung Jawab
Class Lokasi menangani deteksi dan penyimpanan koordinat geografis pengguna menggunakan GPS.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| lokasi_id | int | + | ID lokasi |
| user_id | int | + | ID pengguna |
| latitude | float | + | Koordinat latitude |
| longitude | float | + | Koordinat longitude |
| akurasi | float | + | Akurasi GPS (meter) |
| waktu_deteksi | datetime | + | Waktu deteksi lokasi |
| terakhir_update | datetime | + | Waktu terakhir update |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| deteksi_lokasi | None | dict | + | Deteksi lokasi GPS |
| update_lokasi | latitude, longitude | bool | + | Update koordinat |
| get_koordinat | None | tuple | + | Dapatkan lat/long |
| hapus_lokasi | None | bool | + | Hapus data lokasi |

---

## 5. Kiblat

### Tanggung Jawab
Class Kiblat menghitung dan menampilkan arah kiblat dari lokasi pengguna ke Kaaba Mekah.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| kiblat_id | int | + | ID kiblat |
| user_id | int | + | ID pengguna |
| sudut_kiblat | float | + | Sudut arah kiblat (derajat) |
| koordinat_kaaba | tuple | + | (latitude, longitude) Kaaba |
| metode_hitung | str | + | Metode perhitungan (Umm al-Qura, dll) |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| hitung_sudut | latitude, longitude | float | + | Hitung sudut kiblat |
| get_arah_kiblat | None | str | + | Dapatkan arah kompas |
| set_metode | metode_hitung | None | + | Set metode perhitungan |

---

## 6. Wirid

### Tanggung Jawab
Class Wirid mengelola koleksi wirid dan dzikir dengan informasi teks lengkap.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| wirid_id | int | + | ID wirid |
| judul | str | + | Judul wirid/dzikir |
| teks_arab | str | + | Teks Arab |
| teks_latin | str | + | Teks Latin |
| terjemahan | str | + | Terjemahan bahasa Indonesia |
| kategori | str | + | Kategori (subuh, petang, dll) |
| created_at | datetime | + | Tanggal ditambahkan |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| get_all_wirid | kategori | list | + | Dapatkan semua wirid |
| get_wirid_by_id | wirid_id | Wirid | + | Dapatkan wirid berdasarkan ID |
| search_wirid | kata_kunci | list | + | Cari wirid berdasarkan kata kunci |
| fav_wirid | wirid_id | bool | + | Tambah/hapus favorit |

---

## 7. Dzikir

### Tanggung Jawab
Class Dzikir mengelola fitur tasbih digital dan riwayat pengulangan dzikir.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| dzikir_id | int | + | ID dzikir |
| user_id | int | + | ID pengguna |
| jenis_dzikir | str | + | Jenis dzikir (Subhanallah, Alhamdulillah, Allahu Akbar) |
| jumlah_ulang | int | + | Target jumlah pengulangan |
| jumlah_saat_ini | int | + | Jumlah sudah dikerjakan |
| last_reminder | datetime | + | Waktu terakhir dikerjakan |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| tasbih_naik | None | int | + | Tambah 1 ke counter |
| tasbih_reset | None | None | + | Reset counter ke 0 |
| get_status | None | dict | + | Dapatkan status dzikir |
| simpan_riwayat | None | bool | + | Simpan riwayal pengulangan |
| set_target | jumlah_baru | None | + | Set target pengulangan |

---

## 8. RiwayatDzikir

### Tanggung Jawab
Class RiwayatDzikir mencatat dan menyimpan riwayat aktivitas dzikir pengguna setiap hari.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| riwayat_id | int | + | ID riwayat |
| user_id | int | + | ID pengguna |
| tanggal | date | + | Tanggal riwayat |
| waktu_mulai | datetime | + | Waktu mulai dzikir |
| waktu_selesai | datetime | + | Waktu selesai dzikir |
| jenis_dzikir | str | + | Jenis dzikir yang dilakukan |
| jumlah_ulang | int | + | Jumlah target/ulangan |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| tambah_riwayat | user_id, jenis, jumlah | RiwayatDzikir | + | Tambah entri riwayat |
| get_riwayat_harian | tanggal | list | + | Dapatkan riwayat hari tertentu |
| get_riwayat_bulanan | bulan, tahun | list | + | Dapatkan riwayat bulan |
| hapus_riwayat | riwayat_id | bool | + | Hapus entri riwayat |

---

## 9. Doa

### Tanggung Jawab
Class Doa mengelola koleksi doa sehari-hari dengan teks Arab, Latin, dan terjemahan.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| doa_id | int | + | ID doa |
| judul | str | + | Judul doa |
| teks_arab | str | + | Teks Arab |
| teks_latin | str | + | Teks Latin |
| terjemahan | str | + | Terjemahan bahasa Indonesia |
| kategori | str | + | Kategori doa |
| is_favorit | bool | + | Status favorite |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| get_all_doa | kategori | list | + | Dapatkan semua doa |
| get_doa_by_id | doa_id | Doa | + | Dapatkan doa berdasarkan ID |
| search_doa | kata_kunci | list | + | Cari doa berdasarkan kata kunci |
| set_favorit | doa_id, status | bool | + | Set status favorite |
| get_favorit | None | list | + | Dapatkan daftar doa favorit |

---

## 10. KategoriDoa

### Tanggung Jawab
Class KategoriDoa mengelompokkan doa berdasarkan kategori atau tujuan pengguna.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| kategori_id | int | + | ID kategori |
| nama_kategori | str | + | Nama kategori (pagi, malam, ibadah, dll) |
| deskripsi | str | # | Deskripsi kategori |
| warna_tampilan | str | # | Warna untuk menampilkan di UI |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| add_kategori | nama, deskripsi | KategoriDoa | + | Tambah kategori baru |
| get_all_kategori | None | list | + | Dapatkan semua kategori |
| hapus_kategori | kategori_id | bool | + | Hapus kategori |

---

## 11. Surah

### Tanggung Jawab
Class Surah mengelola daftar 114 surah Al-Qur'an dengan informasi lengkap.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| surah_id | int | + | ID surah |
| nomor | int | + | Nomor urut surah |
| nama | str | + | Nama surah |
| nama_latin | str | + | Nama Latin |
| jumlah_ayat | int | + | Jumlah ayat |
| tempat_turun | str | + | Tempat turun (Mekkah/Madinah) |
| arti_ringkas | str | # | Arti ringkas |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| get_all_surah | None | list | + | Dapatkan semua surah |
| get_surah_by_id | surah_id | Surah | + | Dapatkan surah berdasarkan ID |
| get_surah_by_nomor | nomor | Surah | + | Dapatkan surah berdasarkan nomor |
| search_surah | kata_kunci | list | + | Cari surah berdasarkan nama |

---

## 12. Murottal

### Tanggung Jawab
Class Murottal mengelola pemutar audio untuk recital Al-Qur'an.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| murottal_id | int | + | ID murottal |
| surah_id | int | + | ID surah yang diputar |
| nama_reciter | str | + | Nama pelai (mujawwir) |
| durasi | time | + | Durasi pembacaan |
| path_audio | str | + | Path file audio |
| is_favorite | bool | + | Status favorite reciter |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| play | None | None | + | Memulai pemutaran |
| pause | None | None | + | Menghentikan sementara |
| stop | None | None | + | Menghentikan dan reset |
| set_favorite | murottal_id | bool | + | Set favorit reciter |
| get_list_reciter | None | list | + | Dapatkan daftar reciter |

---

## 13. Pengaturan

### Tanggung Jawab
Class Pengaturan mengelola preferensi pengguna dan konfigurasi aplikasi.

### Atribut

| Nama Atribut | Tipe Data | Visibility | Keterangan |
|--------------|-----------|------------|------------|
| setting_id | int | + | ID setting |
| user_id | int | + | ID pengguna |
| tema | str | + | Tema aplikasi (gelap/cahaya) |
| bahasa | str | + | Bahasa antarmuka |
| notifikasi | bool | + | Status notifikasi |
| suhbat | bool | + | Status sunnah |
| musik_murottal | bool | + | Status audio murottal |

### Method

| Nama Method | Parameter | Return Type | Visibility | Keterangan |
|-------------|-----------|-------------|------------|------------|
| update_setting | kunci, nilai | bool | + | Update seting tertentu |
| get_all_setting | None | dict | + | Dapatkan semua setting |
| reset_default | None | None | + | Reset ke setting default |

---

## Evaluasi dan Penyesuaian Class

### Class yang Digabungkan
1. **Lokasi dan Kiblat**: Class Lokasi digunakan sebagai dasar untuk Class Kiblat. Kedua class memiliki hubungan erat melalui koordinat geografis. Tidak digabungkan karena memiliki tanggung jawab berbeda (Lokasi = deteksi, Kiblat = perhitungan sudut).

### Class yang Ditambahkan
1. **KategoriDoa**: Ditambahkan untuk mendukung fitur pencarian dan pengelompokkan doa sesuai kebutuhan FR-22 dan FR-23.
2. **Murottal**: Ditambahkan untuk memisahkan fitur pemutar audio dari class Surah, karena Murottal memiliki atribut tambahan seperti nama reciter dan path audio.

### Class yang Dihilangkan
Tidak ada class yang dihapus, namun beberapa class direvisi atribut untuk menghindari duplifikasi data dengan User dan JadwalSholat.

### Konsistensi
Setiap class dirancang sesuai tanggung jawab tunggal (Single Responsibility Principle) dan sesuai dengan functional requirements yang telah dibuat. Semua class memiliki hubungan yang saling melengkapi untuk menyokong alur kerja aplikasi SALATIFY dari autentikasi hingga akses konten ibadah.