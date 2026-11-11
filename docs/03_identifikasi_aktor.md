# 03 Identifikasi Aktor

Aktor adalah entity yang berinteraksi dengan sistem aplikasi SALATIFY. Berdasarkan analisis fitur fitur yang tersedia, terdapat tiga aktor utama yang teridentifikasi:

## 1. Pengguna (User)

### Peran
Pengguna adalah aktor utama yang melakukan interaksi seharian dengan aplikasi SALATIFY. Setiap orang yang mendownload dan menginstal aplikasi ini dianggap sebagai pengguna yang memiliki akun sendiri.

### Hak Akses
- dapat mendaftar akun baru (register)
- dapat masuk ke aplikasi (login)
- dapat keluar dari aplikasi (logout)
- dapat mengubah profil pengguna sendiri (nama, foto, preferensi)
- dapat mengakses semua fitur aplikasi yang tersedia
- dapat menyimpan doa favorit
- dapat melihat riwayat dzikir pribadi

### Aktivitas yang Dapat Dilakukan
- Registrasi akun baru dengan nama, email, dan password
- Masuk ke aplikasi menggunakan kredensial akun
- Keluar dari aplikasi
- Memperbarui informasi profil (nama lengkap, foto profil, preferensi notifikasi)
- Melihat jadwal sholat hari ini dan jadwal sholat berikutnya
- Mengaktifkan/menonaktifkan pengingat shalat
- Mengatur waktu pengingat sebelum shalat (contoh: 10 menit, 15 menit, 30 menit sebelum)
- Melihat arah kiblat berdasarkan lokasi saat ini
- Membaca koleksi wirid dan dzikir
- Membaca berbagai doa sehari-hari
- Menambah doa favorit ke daftar favorit
- Mencari doa berdasarkan kata kunci atau kategori
- Memutar audio murottal Al-Qur'an (play, pause, stop)
- Melihat daftar 114 surah Al-Qur'an
- Menyimpan riwayat dzikir harian
- Mengakses menu pengaturan untuk mengubah preferensi aplikasi

---

## 2. Admin Sistem

### Peran
Admin Sistem adalah aktor yang bertanggung jawab atas pengelolaan umum aplikasi SALATIFY. Aktor ini biasanya merupakan tim pengembang atau pemegang hak akses administratif ke backend aplikasi.

### Hak Akses
- dapat melihat statistik penggunaan aplikasi
- dapat mengelola data akun pengguna
- dapat melihat laporan aktivitas pengguna
- dapat memperbarui konten wirid, dzikir, dan doa
- dapat menghapus atau menonaktifkan akun pengguna yang melanggar
- dapat mengonfigurasi pengaturan sistem

### Aktivitas yang Dapat Dilakukan
- Melihat dashboard statistik (jumlah pengguna aktif, frekuensi shalat, dll)
- Melihat daftar daftar pengguna terdaftar
- Menambah, mengedit, atau menghapus konten wirid dan dzikir
- Menambah, mengedit, atau menghapus konten doa
- Mengelola kategori doa
- Melihat laporan penggunaan fitur aplikasi
- Memverifikasi akun pengguna baru
- Mengaktifkan atau menonaktifkan fitur-fitur aplikasi

---

## 3. GPS & Sensor Kompas

### Peran
GPS (Global Positioning System) dan Sensor Kompas adalah aktor teknis yang menyediakan data fisik dari perangkat mobile untuk mendukung perhitungan lokasi dan arah kiblat.

### Hak Akses
- dapat mengakses koordinat geografis (latitude, longitude) pengguna
- dapat mengakses orientasi sudut kompas perangkat
- dapat mengakses accelerometer untuk deteksi orientasi layar

### Aktivitas yang Dapat Dilakukan
- Menyediakan data lokasi geografis pengguna (latitude dan longitude)
- Menghitung sudut arah kiblat (Qibla) dari lokasi pengguna ke Kaaba Mekah
- Menyejajarkan orientasi berdasarkan sensor gyroscope dan kompas magnetometer
- Memantau perubahan lokasi pengguna selama menggunakan aplikasi

*Catatan: Meskipun GPS dan sensor kompas bukan entitas manusia, namun dalam arsitektur sistem, mereka dianggap sebagai aktor karena memiliki kemampuan untuk menyediakan input data yang tidak dapat diberikan oleh pengguna manusia secara langsung.*