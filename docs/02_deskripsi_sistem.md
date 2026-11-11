# 02 Deskripsi Sistem

## Pengertian Aplikasi SALATIFY

SALATIFY (Smart Islamic Companion) adalah aplikasi mobile Android yang dirancang untuk membantu pengguna menjalankan aktivitas ibadah sehari-hari melalui satu aplikasi terintegrasi. Aplikasi ini memanfaatkan teknologi mobile untuk menyediakan jadwal sholat berdasarkan lokasi, pengingat shalat, arah kiblat, koleksi wirid dan dzikir, doa sehari-hari, serta pengacapan Al-Qur'an. Aplikasi dibangun menggunakan kerangka kerja cross-platform Python dengan Kivy dan KivyMD untuk antarmuka pengguna, serta SQLite untuk penyimpanan data lokal di perangkat.

## Latar Belakang

Penghasilan aplikasi SALATIFY muncul dari kebutuhan realitas umat Islam yang semakin modern tetapi masih menjalankan ibadah berdasarkan waktu dan arah tradisional. Dalam kehidupan sehari-hari yang padat, pengguna seringkali lupa waktu shalat atau kesulitan menemukan arah kiblat di lokasi baru. Aplikasi ini dibuat untuk menghadirkan solusi teknologi yang mengesankan dan mudah diakses.

## Tujuan Aplikasi

1. Menyediakan jadwal sholat yang akurat berdasarkan koordinat geografis pengguna.
2. Menampilkan informasi arah kiblat dengan teknologi GPS dan kompas.
3. Mengumpulkan berbagai bentuk ibadah seperti wirid, dzikir, doa, dan Al-Qur'an dalam satu platform.
4. Membantu pengguna menjalani rutinitas ibadah harian yang lebih teratur.
5. Memudahkan akses materi ibadah dalam berbagai bahasa (Arab, Latin, Indonesia).

## Manfaat Aplikasi

1. **Waktu**: Pengganti kalender shalat tradisional, pengingat otomatis tanpa perlu setting manual berulang.
2. **Lokasi**: Menghilangkan ketergantungan pada buku atau web untuk mencari arah kiblat di lokasi baru.
3. **Efisiensi**: satu aplikasi menggantikan berbagai referensi ibadah terpisah (bukuwirid, buku doa, aplikasi qur'an).
4. **Aksesibilitas**: Materi ibadah dapat diakses kapan saja tanpa koneksi internet (untuk konten yang disimpan lokal).

## Cara Kerja Sistem

Alir sistem SALATIFY dapat dijelaskan sebagai berikut:

1. **Inisialisasi**: Pengguna membuka aplikasi dan melakukan proses login/registrasi.
2. **Deteksi Lokasi**: Aplikasi mengakses GPS perangkat untuk mendapatkan koordinat geografis pengguna.
3. **Perhitungan Jadwal**: Sistem menghitung jadwal sholat (Subuh, Dzuhur, Ashar, Maghrib, Isya) berdasarkan lokasi dan tanggal.
4. **Tampilkan Waktu**: Menampilkan jadwal sholat terdekat dan waktu remaining hingga shalat berikutnya.
5. **Arah Kiblat**: Menghitung sudut kiblat dari lokasi pengguna ke Kaaba Mekah.
6. **Akses Konten**: Menampilkan menu wirid, dzikir, doa, dan murottal berdasarkan kategori atau pencarian.
7. **Pengaturan**: Memperbarui preferensi pengguna seperti waktu pengingat, profil, dan notifikasi.
8. **Penyimpanan Data**: Semua data pengguna (favorit, riwayat) disimpan dalam database SQLite lokal.

## Arsitektur Utama

Aplikasi terdiri dari beberapa modul utama yang terintegrasi:
- **Modul Autentikasi**: Login, registrasi, dan manajemen profil.
- **Modul Jadwal**: Menghitung dan menampilkan jadwal sholat.
- **Modul Lokasi**: Mengelola data GPS dan perhitungan arah kiblat.
- **Modul Konten**: Menampilkan wirid, dzikir, doa, dan Al-Qur'an.
- **Modul Notifikasi**: Mengatur pengingat dan notifikasi shalat.
- **Modul Pengaturan**: Mengelola preferensi aplikasi pengguna.