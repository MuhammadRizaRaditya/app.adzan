# 10 Penjelasan Relasi Class

Tabel berikut menjelaskan hubungan antar-class dalam arsitektur SALATIFY beserta alasan setiap jenis relasinya:

| Relasi | Class Terlibat | Jenis Hubungan | Alasan |
|--------|----------------|----------------|--------|
| 1 | User → JadwalSholat | Association | User memiliki banyak jadwal sholat. Setiap pengguna memiliki jadwal pribadi berdasarkan lokasi mereka. |
| 2 | User → PengingatSholat | Association | User mengaktifkan pengingat shalat. Satu pengguna dapat memiliki banyak setting pengingat. |
| 3 | User → Lokasi | Association | User memiliki data lokasi GPS. Setiap pengguna dapat memiliki beberapa entri lokasi jika perlu. |
| 4 | User → Kiblat | Association | User terkait dengan kalkulasi kiblat. Setiap pengguna memiliki sudut kiblat sendiri berdasarkan lokasi. |
| 5 | User → Wirid | Association | User mengakses koleksi wirid. Setiap pengguna dapat membaca dan menyimpan wirid favorit. |
| 6 | User → Dzikir | Association | User memiliki data dzikir pribadi. Setiap pengguna memiliki counter dan target dzikir sendiri. |
| 7 | User → RiwayatDzikir | Association | User memiliki riwayat dzikir harian. Riwayat dicatat berdasarkan setiap sesi dzikir pengguna. |
| 8 | User → Doa | Association | User mengakses koleksi doa. Setiap pengguna dapat menandai doa favorit. |
| 9 | User → KategoriDoa | Association | User menggunakan kategori untuk mengelompokkan doa. Kategori digunakan untuk filter dan pencarian. |
| 10 | User → Surah | Association | User membaca daftar surah Al-Qur'an. Setiap pengguna dapat memutar murottal surah. |
| 11 | User → Murottal | Association | User mendengarkan recital Al-Qur'an. Murottal memiliki reciter favorit per pengguna. |
| 12 | User → Pengaturan | Association | User memiliki preferensi aplikasi. Setiap pengguna dapat mengubah tema, bahasa, dan notifikasi. |

## Relasi antar-class non-User:

| Relasi | Class Terlibat | Jenis Hubungan | Alasan |
|--------|----------------|----------------|--------|
| 13 | JadwalSholat → User | Aggregation | JadwalSholat "memiliki" User dalam sensi bahwa jadwal sholat dibuat berdasarkan user_id. Namun objek JadwalSholat tidak bertanggung jawab menghapus User. |
| 14 | PengingatSholat → User | Aggregation | Setting pengingat terkait dengan pengguna namun bisa diekstrak jika perlu. |
| 15 | Lokasi → User | Aggregation | Data lokasi adalah atribut dari pengguna namun dapat dilaporkan secara statistik. |
| 16 | Kiblat → User | Aggregation | Kalkulasi sudut kiblat menggunakan koordinat dari pengguna. |
| 17 | Dzikir → User | Aggregation | Counter dzikir milik pengguna namun bisa dipisah untuk analitik. |
| 18 | RiwayatDzikir → User | Aggregation | Riwayat dicatat setiap hari namun bisa diekspor untuk laporan. |
| 19 | Doa → KategoriDoa | Association | Doa dikelompokkan ke dalam kategori. Setiap doa dapat memiliki satu kategori. |
| 20 | Surah → Murottal | Composition | Murottal adalah representasi audio dari surah. Jika surah dihapus, murottal-nya juga tidak valid. |
| 21 | Murottal → Surah | Aggregation | Murottal mengandalkan informasi surah_id untuk menampilkan daftar. |

## Penjelasan Spesifik Jenis Hubungan

### Association (Assosiasi)
- Digunakan ketika class saling berinteraksi atau berhubungan tetapi tidak ada kepemilikan yang kuat.
- Contoh: User ↔ JadwalSholat, User ↔ PengingatSholat.
- Setiap user dapat memiliki banyak jadwal/sholat, dan sebaliknya.

### Aggregation
- Digunakan ketika class A "memiliki" class B tetapi B dapat hidup sendiri tanpa A.
- Contoh: User → JadwalSholat (dalam diagram), di mana jadwal dapat tetap ada meskipun user dihapus dari sistem sementara, atau sebaliknya.

### Composition
- Digunakan ketika class A "mempunyai" class B secara eksklusif, B tidak dapat hidup tanpa A.
- Contoh: Surah → Murottal. Murottal adalah audio recital dari surah tertentu. Jika surah dihapus dari database, file audio murottalnya tetap ada tetapi tidak memiliki referensi yang bermakna. Sebaliknya, jika file audio dihapus, informasi surah tetap tersisa.

## Konsistensi dengan Requirement Analysis

Semua relasi di atas konsisten dengan hasil Requirement Analysis di mana:
- Semua fitur utama (FR-01 hingga FR-35) memiliki class yang berhubungan
- Setiap aktor (User, Admin, GPS) memiliki akses yang sesuai dengan relasi class
- Kebutuhan non-fungsional (NFR-01 hingga NFR-10) didukung struktur class yang rapi
- Identifikasi class (dokumen 07) langsung diterjemahkan menjadi diagram di dokumen 08 dan 09

Relasi ini dirancang sesuai prinsip Single Responsibility Setiap class memiliki tanggung jawab satu dan tidak tumpang tindih fungsionalitas dengan class lain.