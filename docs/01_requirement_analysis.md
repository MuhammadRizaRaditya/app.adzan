# 01 Requirement Analysis

## Pengertian Aplikasi SALATIFY

SALATIFY (Smart Islamic Companion) adalah aplikasi mobile Android yang dirancang sebagai pendamping ibadah bagi umat Islam. Aplikasi ini menyediakan berbagai fitur terkait ibadah harian seperti jadwal shalat, pengingat shalat, arah kiblat, wirid dan dzikir, koleksi doa, serta pengacapan Al-Qur'an. Aplikasi dibangun menggunakan teknologi cross-platform dengan Python, Kivy, dan KivyMD untuk antarmuka pengguna, serta SQLite untuk penyimpanan data lokal.

## Latar Belakang Pembuatan Aplikasi

Pembuatan SALATIFY diinisiasi untuk menyelesaikan masalah yang sering dihadapi umat Islam dalam menjalankan ibadah sehari-hari, yaitu:
- Kesulitan mengingat jadwal shalat karena aktivitas sibuk
- Kesulitan menemukan arah kiblat di lokasi yang tidak dikenal
- Kesulitan mengingat wirid dan dzikir harian
- Kesulitan menemukan doa-doah sehari-hari dengan teks lengkap
- Kesulitan mengakses Al-Qur'an dengan pemutaran audio yang mudah

Aplikasi ini bertujuan menjadi solusi satu-stop bagi kebutuhan ibadah harian Muslim.

## Tujuan Aplikasi

1. **Mudah akses jadwal sholat** berdasarkan lokasi pengguna untuk menjalankan ibadah tepat waktu.
2. **Memudahkan pengguna** dalam menemukan arah kiblat menggunakan GPS dan sensor kompas.
3. **Menjadi referensi wirid dan dzikir** dengan teks Arab, latin, dan terjemahan.
4. **Menyediakan koleksi doa** sehari-hari dengan kategori dan fitur pencarian.
5. **Mengakses murottal Al-Qur'an** dengan fitur play, pause, dan skip surah.
6. **Menyimpan riwayat ibadah** pengguna untuk melacak perkembangan spiritual.

## Manfaat Aplikasi

1. **Bagi pengguna**: Membantu menjalankan ibadah dengan lebih teratur dan teratur, mempermudah akses materi ibadah, serta membimbing rutin ibadah harian.
2. **Bagi kelompok**: Mengasah rutin ibadah kelompok, memudahkan koordinasi jadwal shalat, serta meningkatkan kesadaran spiritual.
3. **Bagi masyarakat**: Mewujudkan komunitas Muslim yang lebih beribadah dan memiliki sumber daya ibadah yang mudah didapat.

## Gambaran Umum Cara Kerja Sistem

Sistem SALATIFY bekerja melalui alur berikut:
1. Pengguna mendaftar/login ke aplikasi untuk mengakses fitur-fitur.
2. Aplikasi mendeteksi lokasi pengguna melalui GPS untuk menentukan jadwal sholat dan arah kiblat.
3. Sistem menampilkan jadwal sholat terdekat beserta waktu remaining hingga shalat berikutnya.
4. Pengguna dapat mengaktifkan pengingat shalat dengan waktu yang dapat disesuaikan.
5. Pengguna dapat mengakses koleksi wirid, dzikir, doa, dan murottal Al-Qur'an.
6. Data pengguna seperti riwayat dzikir dan doa favorit disimpan dalam database lokal SQLite.
7. Pengguna dapat mengubah preferensi aplikasi melalui menu pengaturan.

---

## 2. Identifikasi Aktor

| Aktor | Peran | Hak Akses | Aktivitas |
|-------|-------|-----------|-----------|
| **Pengguna Biasa** | Pelanggan aplikasi yang telah mendaftar | - Mendaftar akun baru<br>- Masuk ke aplikasi<br>- Keluar dari aplikasi<br>- Mengubah profil sendiri<br>- Mengakses semua fitur aplikasi | Melihat jadwal shalat, mengaktifkan pengingat, membaca wirid/dzikir, membaca doa, memutar murottal, menyimpan doa favorit, melihat riwayat dzikir |
| **Admin Sistem** | Pengelola sistem aplikasi | - Mengelola data pengguna<br>- Melihat statistik penggunaan<br>- Mengelola konten wirid/dzikir/doa | Mengelola pengguna, melihat laporan aktivitas, memperbarui konten |
| **GPS/Sensor Kompas** | Sumber data lokasi fisik | - Akses data koordinat GPS<br>- Akses orientasi sensor | Menentukan lokasi pengguna, menghitung arah kiblat |

*Catatan: Hanya tiga aktor utama yang identifikasi sesuai dengan skenario penggunaan aplikasi. Aktor tambahan seperti "tamu" tidak dilanjutkan karena semua fitur memerlukan akun pengguna.*